---
title: 'Etapa 2: criar um arquivo corrompido | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cd0b18dc-66c3-4d88-86ef-8e40cb660fae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd5fbe942774192881489e9ea430672f9da5083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573179"
---
# <a name="step-2-creating-a-corrupted-file"></a><span data-ttu-id="44676-102">Etapa 2: Criar um arquivo corrompido</span><span class="sxs-lookup"><span data-stu-id="44676-102">Step 2: Creating a Corrupted File</span></span>
  <span data-ttu-id="44676-103">Para demonstrar a configuração e o tratamento de erros de transformação, você terá que criar um arquivo simples de amostra que no processamento causa a falha de um componente.</span><span class="sxs-lookup"><span data-stu-id="44676-103">In order to demonstrate the configuration and handling of transformation errors, you will have to create a sample flat file that when processed causes a component to fail.</span></span>  
  
 <span data-ttu-id="44676-104">Nesta tarefa, você criará uma cópia de um arquivo simples de amostra existente.</span><span class="sxs-lookup"><span data-stu-id="44676-104">In this task, you will create a copy of an existing sample flat file.</span></span> <span data-ttu-id="44676-105">Você deverá então abrir o arquivo no Bloco de Notas e editar a coluna **CurrencyID** para certificar-se de que não produzirá uma correspondência durante a pesquisa de transformações.</span><span class="sxs-lookup"><span data-stu-id="44676-105">You will then open the file in Notepad and edit the **CurrencyID** column to ensure that it will fail to produce a match during the transformations lookup.</span></span> <span data-ttu-id="44676-106">Quando o arquivo novo for processado, a falha na pesquisa irá causar a falha da transformação Pesquisa de Códigos de Moeda e criará, portanto, uma falha no resto do pacote.</span><span class="sxs-lookup"><span data-stu-id="44676-106">When the new file is processed, the lookup failure will cause the Currency Key Lookup transformation to fail and therefore fail the rest of the package.</span></span> <span data-ttu-id="44676-107">Depois de criar o arquivo de amostra corrompido, você executará o pacote para exibir a falha do pacote.</span><span class="sxs-lookup"><span data-stu-id="44676-107">After you have created the corrupted sample file, you will run the package to view the package failure.</span></span>  
  
### <a name="to-create-a-corrupted-sample-flat-file"></a><span data-ttu-id="44676-108">Para criar um arquivo simples de amostra corrompido</span><span class="sxs-lookup"><span data-stu-id="44676-108">To create a corrupted sample flat file</span></span>  
  
1.  <span data-ttu-id="44676-109">No Bloco de Notas ou em qualquer outro editor de texto, abra o arquivo Currency_VEB.txt.</span><span class="sxs-lookup"><span data-stu-id="44676-109">In Notepad or any other text editor, open the Currency_VEB.txt file.</span></span>  
  
     <span data-ttu-id="44676-110">Os dados de exemplo estão incluídos nos pacotes de lição do SSIS.</span><span class="sxs-lookup"><span data-stu-id="44676-110">The sample data is included with the SSIS Lesson packages.</span></span> <span data-ttu-id="44676-111">Para baixar os dados de exemplo e os pacotes de lição, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="44676-111">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="44676-112">Navegue até [Integration Services exemplos de produto](https://go.microsoft.com/fwlink/?LinkID=267527).</span><span class="sxs-lookup"><span data-stu-id="44676-112">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=267527).</span></span>  
  
    2.  <span data-ttu-id="44676-113">Clique na guia **downloads** .</span><span class="sxs-lookup"><span data-stu-id="44676-113">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="44676-114">Clique no arquivo SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="44676-114">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
2.  <span data-ttu-id="44676-115">Use o recurso Localizar e substituir do editor de texto para localizar todas as instâncias do `VEB` e substituí-las por `BAD` .</span><span class="sxs-lookup"><span data-stu-id="44676-115">Use the text editor's find and replace feature to find all instances of `VEB` and replace them with `BAD`.</span></span>  
  
3.  <span data-ttu-id="44676-116">Na mesma pasta que os outros arquivos de dados de exemplo, salve o arquivo modificado como `Currency_BAD.txt` .</span><span class="sxs-lookup"><span data-stu-id="44676-116">In the same folder as the other sample data files, save the modified file as `Currency_BAD.txt`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="44676-117">Verifique se o `Currency_BAD.txt` está salvo na mesma pasta que os outros arquivos de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="44676-117">Make sure that `Currency_BAD.txt` is saved the same folder as the other sample data files.</span></span>  
  
4.  <span data-ttu-id="44676-118">Feche seu editor de texto.</span><span class="sxs-lookup"><span data-stu-id="44676-118">Close your text editor.</span></span>  
  
### <a name="to-verify-that-an-error-will-occur-during-run-time"></a><span data-ttu-id="44676-119">Para verificar se um erro acontecerá durante o tempo de execução</span><span class="sxs-lookup"><span data-stu-id="44676-119">To verify that an error will occur during run time</span></span>  
  
1.  <span data-ttu-id="44676-120">No menu **Depurar**, clique em **Iniciar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="44676-120">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="44676-121">Na terceira repetição do fluxo de dados, uma transformação Pesquisa de Códigos de Moeda tenta processar o arquivo Currency_BAD.txt e a transformação irá falhar.</span><span class="sxs-lookup"><span data-stu-id="44676-121">On the third iteration of the data flow, the Lookup Currency Key transformation tries to process the Currency_BAD.txt file, and the transformation will fail.</span></span> <span data-ttu-id="44676-122">O fracasso da transformação fará o pacote inteiro falhar.</span><span class="sxs-lookup"><span data-stu-id="44676-122">The failure of the transformation will cause the whole package to fail.</span></span>  
  
2.  <span data-ttu-id="44676-123">No menu **Depuração**, clique em **Parar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="44676-123">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
3.  <span data-ttu-id="44676-124">Na superfície de design, clique na guia **Resultados da Execução** .</span><span class="sxs-lookup"><span data-stu-id="44676-124">On the design surface, click the **Execution Results** tab.</span></span>  
  
4.  <span data-ttu-id="44676-125">Procure no log e verifique se o seguinte erro sem-tratamento ocorreu:</span><span class="sxs-lookup"><span data-stu-id="44676-125">Browse through the log and verify that the following unhandled error occurred:</span></span>  
  
     `[Lookup Currency Key[27]] Error: Row yielded no match during lookup.`  
  
    > [!NOTE]  
    >  <span data-ttu-id="44676-126">O número 27 é a ID do componente.</span><span class="sxs-lookup"><span data-stu-id="44676-126">The number 27 is the ID of the component.</span></span> <span data-ttu-id="44676-127">Esse valor é atribuído quando você cria o fluxo de dados, ou seja, o valor do seu pacote pode ser diferente.</span><span class="sxs-lookup"><span data-stu-id="44676-127">This value is assigned when you build the data flow, and the value in your package may be different.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="44676-128">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="44676-128">Next Steps</span></span>  
 [<span data-ttu-id="44676-129">Etapa 3: Adicionar redirecionamento de fluxo de erro</span><span class="sxs-lookup"><span data-stu-id="44676-129">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
  
