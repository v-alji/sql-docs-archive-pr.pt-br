---
title: Opções (editor de texto-Transact-SQL-IntelliSense) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.Advanced
- VS.ToolsOptionsPages.Text_Editor.SQL_Server_Tools.Advanced
dev_langs:
- TSQL
ms.assetid: 1855d916-5bf9-4d94-b0fb-9f9bb05ff950
author: rothja
ms.author: jroth
ms.openlocfilehash: 2d8f9c865516dc5e4c0ddadbdc908a9b4c8ec366
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575996"
---
# <a name="options-text-editor-transact-sql-intellisense"></a><span data-ttu-id="1f0d6-102">Opções (editor de texto-Transact-SQL-IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="1f0d6-102">Options (Text Editor-Transact-SQL-IntelliSense)</span></span>
  <span data-ttu-id="1f0d6-103">A caixa de diálogo **Opções** permite que você altere as configurações do IntelliSense para o Editor de Consultas [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f0d6-103">The **Options** dialog box lets you change the IntelliSense settings for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="1f0d6-104">Essas configurações estão disponíveis quando, no menu **Ferramentas**, você clica em **Opções**, expande a pasta **Editor de Texto**, expande a pasta **Transact-SQL** e, em seguida, clica em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, expand the **Transact-SQL** folder, and then click **Advanced**.</span></span>  
  
## <a name="transact-sql-intellisense-settings"></a><span data-ttu-id="1f0d6-105">Configurações do IntelliSense do Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1f0d6-105">Transact-SQL IntelliSense Settings</span></span>  
 <span data-ttu-id="1f0d6-106">Especifica as opções do IntelliSense para o Editor de Consultas [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f0d6-106">Specifies the IntelliSense options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span>  
  
### <a name="enable-intellisense"></a><span data-ttu-id="1f0d6-107">Habilitar o IntelliSense</span><span class="sxs-lookup"><span data-stu-id="1f0d6-107">Enable IntelliSense</span></span>  
 <span data-ttu-id="1f0d6-108">Habilita os recursos do IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-108">Enables the IntelliSense features.</span></span> <span data-ttu-id="1f0d6-109">Quando esta caixa não estiver selecionada, as opções do IntelliSense específicas ficarão indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-109">When this box is not selected, the specific IntelliSense options are unavailable.</span></span> <span data-ttu-id="1f0d6-110">Por padrão, esta caixa é selecionada.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-110">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="1f0d6-111">**Sublinhar erros**</span><span class="sxs-lookup"><span data-stu-id="1f0d6-111">**Underline errors**</span></span>  
 <span data-ttu-id="1f0d6-112">Identifica erros de sintaxe e de semântica em instruções [!INCLUDE[tsql](../includes/tsql-md.md)] na janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-112">Identifies syntax and semantic errors in [!INCLUDE[tsql](../includes/tsql-md.md)] statements in the query window.</span></span> <span data-ttu-id="1f0d6-113">Todos os erros e avisos aparecem em vermelho.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-113">All errors and warnings appear in red.</span></span> <span data-ttu-id="1f0d6-114">Só há suporte para erros e avisos nas instruções [!INCLUDE[tsql](../includes/tsql-md.md)] para as quais o IntelliSense foi implementado.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-114">Errors and warnings are supported only for the [!INCLUDE[tsql](../includes/tsql-md.md)] statements for which IntelliSense has been implemented.</span></span> <span data-ttu-id="1f0d6-115">Por padrão, esta caixa é selecionada.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-115">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="1f0d6-116">**Instruções para estrutura de tópicos**</span><span class="sxs-lookup"><span data-stu-id="1f0d6-116">**Outline statements**</span></span>  
 <span data-ttu-id="1f0d6-117">Habilita o recurso de estrutura de tópicos quando um arquivo é aberto.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-117">Enables the outlining feature when a file is opened.</span></span> <span data-ttu-id="1f0d6-118">Isso cria blocos recolhíveis de código [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f0d6-118">This creates collapsible blocks of [!INCLUDE[tsql](../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="1f0d6-119">Por padrão, esta caixa é selecionada.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-119">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="1f0d6-120">**Tamanho máximo de script**</span><span class="sxs-lookup"><span data-stu-id="1f0d6-120">**Maximum script size**</span></span>  
 <span data-ttu-id="1f0d6-121">Especifica o tamanho no qual a funcionalidade IntelliSense é desabilitada.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-121">Specifies the size at which IntelliSense functionality is disabled.</span></span> <span data-ttu-id="1f0d6-122">Se um script exceder o tamanho especificado, uma mensagem de aviso será emitida.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-122">If a script exceeds the specified size, a warning message is issued.</span></span> <span data-ttu-id="1f0d6-123">Todos os recursos do IntelliSense, exceto a codificação de cor, são desabilitados nessa janela do editor.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-123">All IntelliSense features, except color coding, are disabled for that editor window.</span></span> <span data-ttu-id="1f0d6-124">O IntelliSense é habilitado novamente quando texto suficiente é excluído para reduzir o tamanho de script para o limite.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-124">IntelliSense is reenabled when enough text is deleted to reduce the script size to under the limit.</span></span> <span data-ttu-id="1f0d6-125">A habilitação do IntelliSense para tamanhos de script grandes pode prejudicar o desempenho em computadores lentos.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-125">Enabling IntelliSense for large script sizes can decrease performance on slow computers.</span></span> <span data-ttu-id="1f0d6-126">Os tamanhos permitidos são 100 KB, 500 KB, 1 MB, 2 MB e Ilimitado.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-126">The allowed sizes are 100 KB, 500 KB, 1 MB, 2 MB, and Unlimited.</span></span> <span data-ttu-id="1f0d6-127">O padrão é 1 MB.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-127">The default is 1 MB.</span></span>  
  
 <span data-ttu-id="1f0d6-128">**Caixas para nomes de funções internas**</span><span class="sxs-lookup"><span data-stu-id="1f0d6-128">**Casing for built-in function names**</span></span>  
 <span data-ttu-id="1f0d6-129">Especifica se os nomes das funções internas do [!INCLUDE[tsql](../includes/tsql-md.md)] incluídos nas listas de conclusão usam letras maiúsculas, como DATEADD, ou minúsculas, como dateadd.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-129">Specifies whether the names of built-in [!INCLUDE[tsql](../includes/tsql-md.md)] functions that are included in completion lists use uppercase letters, such as DATEADD; or lowercase letters, such as dateadd.</span></span> <span data-ttu-id="1f0d6-130">Selecione a opção que atende melhor às convenções de codificação do [!INCLUDE[tsql](../includes/tsql-md.md)] em uso.</span><span class="sxs-lookup"><span data-stu-id="1f0d6-130">Select the option that best matches the [!INCLUDE[tsql](../includes/tsql-md.md)] coding conventions that you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f0d6-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1f0d6-131">See Also</span></span>  
 [<span data-ttu-id="1f0d6-132">Solucionando problemas do IntelliSense &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1f0d6-132">Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;</span></span>](../relational-databases/scripting/troubleshooting-intellisense.md)  
  
  
