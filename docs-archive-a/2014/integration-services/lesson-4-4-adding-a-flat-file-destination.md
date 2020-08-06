---
title: 'Etapa 4: adicionar um destino de arquivo simples | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f4088de3-16d8-419c-96a1-a2cd005d0a5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eff65f4a94a412d55af8055e302195f87ae4cdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683117"
---
# <a name="step-4-adding-a-flat-file-destination"></a><span data-ttu-id="89cb7-102">Etapa 4: Adicionar um destino de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="89cb7-102">Step 4: Adding a Flat File Destination</span></span>
  <span data-ttu-id="89cb7-103">A saída de erro da transformação Pesquisa de Códigos de Moeda redireciona para a transformação Script todas as linhas de dados que falharam na operação de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="89cb7-103">The error output of the Lookup Currency Key transformation redirects to the Script transformation any data rows that failed the lookup operation.</span></span> <span data-ttu-id="89cb7-104">Para aprimorar as informações sobre os erros que ocorreram, a transformação Script executa um script que adquire a descrição de erros.</span><span class="sxs-lookup"><span data-stu-id="89cb7-104">To enhance information about the errors that occurred, the Script transformation runs a script that gets the description of errors.</span></span>  
  
 <span data-ttu-id="89cb7-105">Nessa tarefa, você salvará todas essas informações sobre as linhas com falha em um arquivo delimitado, para processamento posterior.</span><span class="sxs-lookup"><span data-stu-id="89cb7-105">In this task, you will save all this information about the failed rows to a delimited file for later processing.</span></span> <span data-ttu-id="89cb7-106">Para salvar as linhas com falha, você deve adicionar e configurar um gerenciador de conexões de arquivo simples para o arquivo de texto que conterá os dados de erro e um arquivo simples de destino.</span><span class="sxs-lookup"><span data-stu-id="89cb7-106">To save the failed rows, you must add and configure a Flat File connection manager for the text file that will contain the error data and a Flat File destination.</span></span> <span data-ttu-id="89cb7-107">Ao definir propriedades no gerenciador de conexões de arquivo simples que o arquivo simples usa, você pode especificar como o destino do arquivo simples formata e escreve o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="89cb7-107">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="89cb7-108">Para obter mais informações, consulte [Gerenciador de conexões de arquivo simples](connection-manager/file-connection-manager.md) e [destino de arquivo simples](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="89cb7-108">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md) and [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
### <a name="to-add-and-configure-a-flat-file-destination"></a><span data-ttu-id="89cb7-109">Para adicionar e configurar um destino de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="89cb7-109">To add and configure a Flat File destination</span></span>  
  
1.  <span data-ttu-id="89cb7-110">Clique na guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="89cb7-110">Click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="89cb7-111">Na **Caixa de Ferramentas do SSIS**, expanda **Outros**e arraste **Destino de Arquivo Simples** para a superfície de design de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="89cb7-111">In the **SSIS Toolbox**, expand **Other**, and drag **Flat File Destination** onto the data flow design surface.</span></span> <span data-ttu-id="89cb7-112">Coloque **Destino de Arquivo Simples** diretamente embaixo da transformação **Obter Descrição do Erro** .</span><span class="sxs-lookup"><span data-stu-id="89cb7-112">Put the **Flat File Destination** directly underneath the **Get Error Description** transformation.</span></span>  
  
3.  <span data-ttu-id="89cb7-113">Clique na transformação **Obter Descrição do Erro** e arraste a seta verde sobre o novo **Destino de Arquivo Simples**.</span><span class="sxs-lookup"><span data-stu-id="89cb7-113">Click the **Get Error Description** transformation, and then drag the green arrow onto the new **Flat File Destination**.</span></span>  
  
4.  <span data-ttu-id="89cb7-114">Na superfície de design de **Fluxo de Dados** , clique em **Destino de Arquivo Simples** , na recém-adicionada transformação **Destino de Arquivo Simples** , e altere o nome para **Linhas com Falha**.</span><span class="sxs-lookup"><span data-stu-id="89cb7-114">On the **Data Flow** design surface, click **Flat File Destination** in the newly added **Flat File Destination** transformation, and change the name to **Failed Rows**.</span></span>  
  
5.  <span data-ttu-id="89cb7-115">Clique com o botão direito do mouse na transformação **Linhas com Falha** , clique em **Editar**e, no **Editor de Destino de Arquivo Simples**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="89cb7-115">Right-click the **Failed Rows** transformation, click **Edit**, and then in the **Flat File Destination Editor**, click **New**.</span></span>  
  
6.  <span data-ttu-id="89cb7-116">Na caixa de diálogo **Formato de Arquivo Simples** , verifique se **Delimitado** está selecionado e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="89cb7-116">In the **Flat File Format** dialog box, verify that **Delimited** is selected, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="89cb7-117">No **Editor do Gerenciador de conexões de arquivo simples**, na caixa nome do Gerenciador de **conexões** , digite `Error Data` .</span><span class="sxs-lookup"><span data-stu-id="89cb7-117">In the **Flat File Connection Manager Editor**, in the **Connection Manager Name** box type `Error Data`.</span></span>  
  
8.  <span data-ttu-id="89cb7-118">Na caixa de diálogo **Editor do Gerenciador de Conexões de Arquivo Simples** , clique em **Procurar**e localize a pasta em que o arquivo será armazenado.</span><span class="sxs-lookup"><span data-stu-id="89cb7-118">In the **Flat File Connection Manager Editor** dialog box, click **Browse**, and locate the folder in which to store the file.</span></span>  
  
9. <span data-ttu-id="89cb7-119">Na caixa de diálogo **abrir** , em **nome do arquivo**, digite e, em `ErrorOutput.txt` seguida, clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="89cb7-119">In the **Open** dialog box, for **File name**, type `ErrorOutput.txt`, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="89cb7-120">Na caixa de diálogo **Editor do Gerenciador de Conexões de Arquivo Simples** , verifique se a caixa **Localidade** contém Inglês (Estados Unidos) e **Página de código** contém 1252 (ANSI – Latim I).</span><span class="sxs-lookup"><span data-stu-id="89cb7-120">In the **Flat File Connection Manager Editor** dialog box, verify that the **Locale** box contains English (United States) and **Code page** contains 1252 (ANSI -Latin I).</span></span>  
  
11. <span data-ttu-id="89cb7-121">No painel de opções, clique em **Colunas**.</span><span class="sxs-lookup"><span data-stu-id="89cb7-121">In the options pane, click **Columns**.</span></span>  
  
     <span data-ttu-id="89cb7-122">Observe que, além das colunas do arquivo de dados de origem, três colunas novas estão presentes: ErrorCode, ErrorColumn e ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="89cb7-122">Notice that, in addition to the columns from the source data file, three new columns are present: ErrorCode, ErrorColumn, and ErrorDescription.</span></span> <span data-ttu-id="89cb7-123">Essas colunas são geradas pela saída de erro da transformação Pesquisa de Códigos de Moeda e pelo script na transformação Obter Descrição do Erro e podem ser usadas para diagnosticar a causa da linha com falha.</span><span class="sxs-lookup"><span data-stu-id="89cb7-123">These columns are generated by the error output of the Lookup Currency Key transformation and by the script in the Get Error Description transformation, and can be used to troubleshoot the cause of the failed row.</span></span>  
  
12. <span data-ttu-id="89cb7-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="89cb7-124">Click **OK**.</span></span>  
  
13. <span data-ttu-id="89cb7-125">No **Editor de Destino de Arquivo Simples**, desmarque a caixa de seleção **Substituir dados no arquivo** .</span><span class="sxs-lookup"><span data-stu-id="89cb7-125">In the **Flat File Destination Editor**, clear the **Overwrite data in the file** check box.</span></span>  
  
     <span data-ttu-id="89cb7-126">Ao desmarcar essa caixa de seleção, os erros sobre as execuções de vários pacotes serão mantidos.</span><span class="sxs-lookup"><span data-stu-id="89cb7-126">Clearing this check box persists the errors over multiple package executions.</span></span>  
  
14. <span data-ttu-id="89cb7-127">No **Editor de Destino de Arquivo Simples**, clique em **Mapeamentos** para verificar se todas as colunas estão corretas.</span><span class="sxs-lookup"><span data-stu-id="89cb7-127">In the **Flat File Destination Editor**, click **Mappings** to verify that all the columns are correct.</span></span> <span data-ttu-id="89cb7-128">Como alternativa, você pode renomear as colunas no destino.</span><span class="sxs-lookup"><span data-stu-id="89cb7-128">Optionally, you can rename the columns in the destination.</span></span>  
  
15. <span data-ttu-id="89cb7-129">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="89cb7-129">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="89cb7-130">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="89cb7-130">Next Steps</span></span>  
 [<span data-ttu-id="89cb7-131">Etapa 5: Testar o pacote de tutorial da Lição 4</span><span class="sxs-lookup"><span data-stu-id="89cb7-131">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](../integration-services/lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
  
