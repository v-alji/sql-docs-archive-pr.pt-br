---
title: Salvar um plano de execução no formato XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- XML query plans [SQL Server]
- opening execution plans
- XML Showplans [SQL Server]
- execution plans [SQL Server], saving
- saving execution plans
ms.assetid: c439e53b-56f3-4442-97c6-dabd48a203d8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 84ed341d186993ed77260e8361156b324c597839
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575781"
---
# <a name="save-an-execution-plan-in-xml-format"></a><span data-ttu-id="575df-102">Salvar um plano de execução em formato XML</span><span class="sxs-lookup"><span data-stu-id="575df-102">Save an Execution Plan in XML Format</span></span>
  <span data-ttu-id="575df-103">Use o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para salvar planos de execução como um arquivo XML e abri-los para exibição.</span><span class="sxs-lookup"><span data-stu-id="575df-103">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to save execution plans as an XML file, and to open them for viewing.</span></span>  
  
 <span data-ttu-id="575df-104">Para usar o recurso plano de execução em [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], ou usar as opções SET Showplan XML, os usuários devem ter as permissões apropriadas para executar a consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] para qual um plano de execução está sendo gerado, e deve ser concedida a permissão SHOWPLAN para todos os bancos de dados referenciados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="575df-104">To use the execution plan feature in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or to use the XML Showplan SET options, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which an execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-save-a-query-plan-by-using-the-xml-showplan-set-options"></a><span data-ttu-id="575df-105">Para salvar um plano de consulta usando as opções SET Showplan XML</span><span class="sxs-lookup"><span data-stu-id="575df-105">To save a query plan by using the XML Showplan SET options</span></span>  
  
1.  <span data-ttu-id="575df-106">Em [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] abra um editor de consulta e conecte a [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="575df-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] open a query editor and connect to [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="575df-107">Ative o SHOWPLAN_XML com a instrução seguinte:</span><span class="sxs-lookup"><span data-stu-id="575df-107">Turn SHOWPLAN_XML on with the following statement:</span></span>  
  
    ```  
    SET SHOWPLAN_XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="575df-108">Para ativar o STATISTICS XML, use a instrução seguinte:</span><span class="sxs-lookup"><span data-stu-id="575df-108">To turn STATISTICS XML on, use the following statement:</span></span>  
  
    ```  
    SET STATISTICS XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="575df-109">O SHOWPLAN_XML gera informações de plano de execução de consulta de tempo de compilação para uma consulta, mas não executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="575df-109">SHOWPLAN_XML generates compile-time query execution plan information for a query, but does not execute the query.</span></span> <span data-ttu-id="575df-110">O STATISTICS XML gera informações de plano de execução de consulta em tempo de execução para uma consulta e executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="575df-110">STATISTICS XML generates run-time query execution plan information for a query, and executes the query.</span></span>  
  
3.  <span data-ttu-id="575df-111">Execute uma consulta.</span><span class="sxs-lookup"><span data-stu-id="575df-111">Execute a query.</span></span> <span data-ttu-id="575df-112">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="575df-112">Example:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SET SHOWPLAN_XML ON;  
    GO  
    -- Execute a query.  
    SELECT BusinessEntityID   
    FROM HumanResources.Employee  
    WHERE NationalIDNumber = '509647174';  
    GO  
    SET SHOWPLAN_XML OFF;  
    ```  
  
4.  <span data-ttu-id="575df-113">No painel **Resultados** , clique com o botão direito do mouse em **Plano de execução XML do Microsoft SQL Server** que contém o plano de consulta e clique em **Salvar Resultados Como**.</span><span class="sxs-lookup"><span data-stu-id="575df-113">In the **Results** pane, right-click the **Microsoft SQL Server XML Showplan** that contains the query plan, and then click **Save Results As**.</span></span>  
  
5.  <span data-ttu-id="575df-114">Na caixa de diálogo **Salvar** \<Grid or Text> **Resultados**, na caixa **Salvar como tipo**, clique em **Todos os arquivos (\*.\*)** .</span><span class="sxs-lookup"><span data-stu-id="575df-114">In the **Save** \<Grid or Text> **Results** dialog box, in the **Save as type** box, click **All files (\*.\*)**.</span></span>  
  
6.  <span data-ttu-id="575df-115">Na caixa **Nome do arquivo**, forneça um nome no formato \<name**>.sqlplan\*\* e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="575df-115">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-save-an-execution-plan-by-using-sql-server-management-studio-options"></a><span data-ttu-id="575df-116">Para salvar um plano de execução usando opções do SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="575df-116">To save an execution plan by using SQL Server Management Studio options</span></span>  
  
1.  <span data-ttu-id="575df-117">Gere um plano de execução estimado ou um plano de execução atual usando [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="575df-117">Generate either an estimated execution plan or an actual execution plan by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="575df-118">Para obter mais informações, veja [Exibir o plano de execução estimado](display-the-estimated-execution-plan.md) ou [Exibir um plano de execução real](display-an-actual-execution-plan.md).</span><span class="sxs-lookup"><span data-stu-id="575df-118">For more information, see [Display the Estimated Execution Plan](display-the-estimated-execution-plan.md) or [Display an Actual Execution Plan](display-an-actual-execution-plan.md).</span></span>  
  
2.  <span data-ttu-id="575df-119">Na guia **Plano de execução** do painel de resultados, clique com o botão direito do mouse no plano de execução gráfico e escolha **Salvar Plano de Execução Como**.</span><span class="sxs-lookup"><span data-stu-id="575df-119">In the **Execution plan** tab of the results pane, right-click the graphical execution plan, and choose **Save Execution Plan As**.</span></span>  
  
     <span data-ttu-id="575df-120">Como alternativa, você também pode escolher **Salvar Plano de Execução Como** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="575df-120">As an alternative, you can also choose **Save Execution Plan As** on the **File** menu.</span></span>  
  
3.  <span data-ttu-id="575df-121">Na caixa de diálogo **Salvar Como**, verifique se a opção **Salvar como tipo** está definida como **Arquivos de Plano de Execução (\*.sqlplan)** .</span><span class="sxs-lookup"><span data-stu-id="575df-121">In the **Save As** dialog box, make sure that the **Save as type** is set to **Execution Plan Files (\*.sqlplan)**.</span></span>  
  
4.  <span data-ttu-id="575df-122">Na caixa **Nome do arquivo**, forneça um nome no formato \<name**>.sqlplan\*\* e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="575df-122">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-open-a-saved-xml-query-plan-in-sql-server-management-studio"></a><span data-ttu-id="575df-123">Para abrir um plano de consulta XML salvo em SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="575df-123">To open a saved XML query plan in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="575df-124">Em [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Arquivo** , escolha **Abrir**e então clique em **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="575df-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, choose **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="575df-125">Na caixa de diálogo **Abrir Arquivo**, defina **Arquivos de tipo** para **Arquivos de Plano de Execução (\*.sqlplan)** para gerar uma lista filtrada dos arquivos de plano de consulta XML salvos.</span><span class="sxs-lookup"><span data-stu-id="575df-125">In the **Open File** dialog box, set **Files of type** to **Execution Plan Files (\*.sqlplan)** to produce a filtered list of saved XML query plan files.</span></span>  
  
3.  <span data-ttu-id="575df-126">Selecione o arquivo plano consulta XML que você quer exibir e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="575df-126">Select the XML query plan file that you want to view, and click **Open**.</span></span>  
  
     <span data-ttu-id="575df-127">Como alternativa, no Windows Explorer, clique duas vezes em um arquivo com a extensão **.sqlplan**.</span><span class="sxs-lookup"><span data-stu-id="575df-127">As an alternative, in Windows Explorer, double-click a file with extension **.sqlplan**.</span></span> <span data-ttu-id="575df-128">O plano abre em [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="575df-128">The plan opens in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575df-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="575df-129">See Also</span></span>  
 <span data-ttu-id="575df-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="575df-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span></span>  
 [<span data-ttu-id="575df-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="575df-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
  
