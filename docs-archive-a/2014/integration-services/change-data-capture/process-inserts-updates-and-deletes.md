---
title: Processar inserções, atualizações e exclusões | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],processing data
ms.assetid: 13a84d21-2623-4efe-b442-4125a7a2d690
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67f016aaf4f7f83c0fa506966c4e78f5b8fadef6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569585"
---
# <a name="process-inserts-updates-and-deletes"></a><span data-ttu-id="9bd1b-102">Processar inserções, atualizações e exclusões</span><span class="sxs-lookup"><span data-stu-id="9bd1b-102">Process Inserts, Updates, and Deletes</span></span>
  <span data-ttu-id="9bd1b-103">No fluxo de dados de um pacote do Integration Services, que executa uma carga incremental de dados de alteração, a segunda tarefa serve para separar inserções, atualizações e exclusões.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-103">In the data flow of an Integration Services package that performs an incremental load of change data, the second task is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="9bd1b-104">Em seguida, você pode usar comandos apropriados para aplicá-los ao destino.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-104">Then, you can use appropriate commands to apply them to the destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9bd1b-105">A primeira tarefa na criação do fluxo de dados de um pacote que realize uma carga incremental de dados de alteração é configurar o componente de origem que executa a consulta que recupera os dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-105">The first task in designing the data flow of a package that performs an incremental load of change data is to configure the source component that runs the query that retrieves the change data.</span></span> <span data-ttu-id="9bd1b-106">Para obter mais informações sobre esse componente, consulte [Recuperar e compreender os dados de alteração](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="9bd1b-106">For more information about this component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span> <span data-ttu-id="9bd1b-107">Para obter uma descrição do processo geral para criar um pacote que realiza uma carga incremental de dados de alteração, consulte [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="9bd1b-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="associating-friendly-values-to-separate-inserts-updates-and-deletes"></a><span data-ttu-id="9bd1b-108">Associando valores amigáveis para separar inserções, atualizações e exclusões</span><span class="sxs-lookup"><span data-stu-id="9bd1b-108">Associating Friendly Values to Separate Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="9bd1b-109">Na consulta de exemplo que recupera dados de alteração, a função **cdc.fn_cdc_get_net_changes_<capture_instance>** retorna somente a coluna de metadados chamada **__$operation**.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-109">In the example query that retrieves change data, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns only the column of metadata named **__$operation**.</span></span> <span data-ttu-id="9bd1b-110">Esta coluna de metadados contém um valor ordinal que indica qual operação causou a alteração.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-110">This metadata column contains an ordinal value that indicates which operation caused the change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9bd1b-111">Para obter mais informações sobre a consulta que usa chamadas da função **cdc.fn_cdc_get_net_changes_<capture_instance>** , consulte [Criar a função para recuperar os dados de alteração](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="9bd1b-111">For more information about the query that uses calls the **cdc.fn_cdc_get_net_changes_<capture_instance>** function, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
 <span data-ttu-id="9bd1b-112">Corresponder um valor ordinal a sua operação correspondente não é tão fácil quanto usar um mnemônico da operação.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-112">Matching an ordinal value to its corresponding operation is not as easy as using a mnemonic of the operation.</span></span> <span data-ttu-id="9bd1b-113">Por exemplo, 'D' pode representar facilmente uma operação de exclusão e 'I' representar uma operação de inserção.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-113">For example, 'D' can easily represent a delete operation and 'I' represent an insert operation.</span></span> <span data-ttu-id="9bd1b-114">A consulta de exemplo criada no tópico, [Criando a função para recuperar os dados de alteração](create-the-function-to-retrieve-the-change-data.md), faz essa conversão de um valor ordinal para um valor de cadeia de caracteres amigável que retorna uma nova coluna.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-114">The example query that was created in the topic, [Creating the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md), makes this conversion from an ordinal value to a friendly string value that is returned in a new column.</span></span> <span data-ttu-id="9bd1b-115">O seguinte segmento de código mostra esta conversão:</span><span class="sxs-lookup"><span data-stu-id="9bd1b-115">The following segment of code shows this conversion:</span></span>  
  
```  
select   
    ...  
    case __$operation  
        when 1 then 'D'  
        when 2 then 'I'  
        when 4 then 'U'  
        else null  
     end as CDC_OPERATION  
```  
  
## <a name="configuring-a-conditional-split-transformation-to-direct-inserts-updates-and-deletes"></a><span data-ttu-id="9bd1b-116">Configurando uma transformação de divisão condicional para direcionar inserções, atualizações e exclusões</span><span class="sxs-lookup"><span data-stu-id="9bd1b-116">Configuring a Conditional Split Transformation to Direct Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="9bd1b-117">Para direcionar linhas de dados de alteração para uma de três saídas, a transformação de Divisão Condicional é ideal.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-117">To direct rows of change data to one of three outputs, the Conditional Split transformation is ideal.</span></span> <span data-ttu-id="9bd1b-118">A transformação apenas verifica o valor da coluna **CDC_OPERATION** em cada linha e determina se essa alteração foi uma inserção, atualização ou exclusão.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-118">The transformation just checks the value of the **CDC_OPERATION** column in each row and determines whether that change was an insert, update, or delete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9bd1b-119">A coluna de CDC_OPERATION contém um valor da cadeia de caracteres amigável derivado do valor numérico na coluna **__$operation** .</span><span class="sxs-lookup"><span data-stu-id="9bd1b-119">The CDC_OPERATION column contains a friendly string value derived from the numeric value in the **__$operation** column.</span></span>  
  
#### <a name="to-split-inserts-updates-and-deletes-for-processing-by-using-a-conditional-split-transformation"></a><span data-ttu-id="9bd1b-120">Para dividir inserções, atualizações e exclusões por processamento usando uma transformação de Divisão Condicional</span><span class="sxs-lookup"><span data-stu-id="9bd1b-120">To split inserts, updates, and deletes for processing by using a Conditional Split transformation</span></span>  
  
1.  <span data-ttu-id="9bd1b-121">Na guia **Fluxo de Dados** , adicione uma transformação de Divisão Condicional.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-121">On the **Data Flow** tab, add a Conditional Split transformation.</span></span>  
  
2.  <span data-ttu-id="9bd1b-122">Conecte a saída da origem OLE DB à transformação de Divisão Condicional.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-122">Connect the output of the OLE DB source to the Conditional Split transformation.</span></span>  
  
3.  <span data-ttu-id="9bd1b-123">No **Editor de Transformação de Divisão Condicional**, no painel inferior do editor, digite as três linhas a seguir para designar as três saídas</span><span class="sxs-lookup"><span data-stu-id="9bd1b-123">In the **Conditional Split Transformation Editor**, in the lower pane of the editor, enter the following three lines to designate the three outputs</span></span>  
  
    1.  <span data-ttu-id="9bd1b-124">Digite uma linha com a condição `CDC_OPERATION == "I"` para direcionar as linhas inseridas para a saída para inserções.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-124">Enter a line with the condition `CDC_OPERATION == "I"` to direct inserted rows to the output for inserts.</span></span>  
  
    2.  <span data-ttu-id="9bd1b-125">Digite uma linha com a condição `CDC_OPERATION == "U"` para direcionar as linhas atualizadas para a saída para atualizações.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-125">Enter a line with the condition `CDC_OPERATION == "U"` to direct updated rows to the output for updates.</span></span>  
  
    3.  <span data-ttu-id="9bd1b-126">Digite uma linha com a condição `CDC_OPERATION == "D"` para direcionar as linhas excluídas para a saída para exclusões.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-126">Enter a line with the condition `CDC_OPERATION == "D"` to direct deleted rows to the output for deletes.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="9bd1b-127">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="9bd1b-127">Next Step</span></span>  
 <span data-ttu-id="9bd1b-128">Após você dividir as linhas por processamento, a próxima etapa é aplicar as alterações ao destino.</span><span class="sxs-lookup"><span data-stu-id="9bd1b-128">After you split the rows for processing, the next step is to apply the changes to the destination.</span></span>  
  
 <span data-ttu-id="9bd1b-129">**Próximo tópico:** [Aplicar as alterações ao destino](apply-the-changes-to-the-destination.md)</span><span class="sxs-lookup"><span data-stu-id="9bd1b-129">**Next topic:** [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd1b-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9bd1b-130">See Also</span></span>  
 <span data-ttu-id="9bd1b-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="9bd1b-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span></span>  
 [<span data-ttu-id="9bd1b-132">Dividir um conjunto de dados por meio da transformação Divisão Condicional</span><span class="sxs-lookup"><span data-stu-id="9bd1b-132">Split a Dataset by Using the Conditional Split Transformation</span></span>](../data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
