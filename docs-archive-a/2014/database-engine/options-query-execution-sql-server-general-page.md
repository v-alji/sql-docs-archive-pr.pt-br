---
title: Opções (página execução da consulta-SQL Server-geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryExecution.SqlServer.SqlExecutionGeneral
ms.assetid: 3f8d59bc-3f97-4e5d-8b86-5ac670d20780
author: rothja
ms.author: jroth
ms.openlocfilehash: eaa95293636d02674fb720dcd1b8146279f78e72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582589"
---
# <a name="options-query-execution-sql-server-general-page"></a><span data-ttu-id="e089f-102">Opções (página execução da consulta-SQL Server-geral)</span><span class="sxs-lookup"><span data-stu-id="e089f-102">Options (Query Execution-SQL Server-General Page)</span></span>
  <span data-ttu-id="e089f-103">Use essa página a fim de especificar as opções para executar consultas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e089f-103">Use this page to specify the options for running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="e089f-104">As alterações feitas nessas opções são aplicadas apenas a novas consultas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e089f-104">Changes to these options are only applied to new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="e089f-105">Para alterar as opções de uma consulta atual, clique em **Opções de Consulta** no menu **Consulta** ou clique com o botão direito do mouse em uma janela Consulta do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e selecione **Opções de Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e089f-105">To change the options for a current query, click **Query Options** on the **Query** menu, or in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window right-click and select **Query Options**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e089f-106">Opções</span><span class="sxs-lookup"><span data-stu-id="e089f-106">Options</span></span>  
 <span data-ttu-id="e089f-107">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="e089f-107">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="e089f-108">O valor padrão 0 indica que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] esperará por resultados até que todos os resultados tenham sido recebidos.</span><span class="sxs-lookup"><span data-stu-id="e089f-108">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="e089f-109">Forneça um valor maior que 0 se desejar que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pare a consulta após obter o número especificado de linhas.</span><span class="sxs-lookup"><span data-stu-id="e089f-109">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="e089f-110">Para desligar essa opção (de forma que todas as linhas sejam retornadas), especifique SET ROWCOUNT 0.</span><span class="sxs-lookup"><span data-stu-id="e089f-110">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="e089f-111">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="e089f-111">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="e089f-112">O valor padrão de 2.147.483.647 bytes, indica que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fornecerá campos de dados completos até o limite dos campos de dados `text` e `ntext`.</span><span class="sxs-lookup"><span data-stu-id="e089f-112">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide complete data fields up to the limit of `text` and `ntext` data fields.</span></span> <span data-ttu-id="e089f-113">Forneça um número menor para limitar os resultados no caso de valores grandes.</span><span class="sxs-lookup"><span data-stu-id="e089f-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="e089f-114">Colunas maiores que o número fornecido serão truncadas.</span><span class="sxs-lookup"><span data-stu-id="e089f-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="e089f-115">**Tempo limite de execução**</span><span class="sxs-lookup"><span data-stu-id="e089f-115">**Execution time-out**</span></span>  
 <span data-ttu-id="e089f-116">Define o valor padrão na caixa de diálogo **Nova Conexão** .</span><span class="sxs-lookup"><span data-stu-id="e089f-116">Sets the default value in the **New Connection** dialog box.</span></span> <span data-ttu-id="e089f-117">Use essa caixa de rotação para informar ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o número de segundos de espera antes de cancelar a consulta.</span><span class="sxs-lookup"><span data-stu-id="e089f-117">Use this spin box to tell [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="e089f-118">Um valor de 0 indica uma espera infinita ou nenhum tempo limite. Esse valor é 0 em uma nova instalação.</span><span class="sxs-lookup"><span data-stu-id="e089f-118">A value of 0 indicates an infinite wait, or no time-out. This value is 0 on a new installation.</span></span>  
  
 <span data-ttu-id="e089f-119">**Separador de lotes**</span><span class="sxs-lookup"><span data-stu-id="e089f-119">**Batch separator**</span></span>  
 <span data-ttu-id="e089f-120">Digite uma palavra que você usa para separar instruções [!INCLUDE[tsql](../includes/tsql-md.md)] em lotes.</span><span class="sxs-lookup"><span data-stu-id="e089f-120">Type a word that you use to separate [!INCLUDE[tsql](../includes/tsql-md.md)] statements into batches.</span></span> <span data-ttu-id="e089f-121">O padrão é GO.</span><span class="sxs-lookup"><span data-stu-id="e089f-121">The default is GO.</span></span>  
  
 <span data-ttu-id="e089f-122">**Por padrão, abra consultas novas no Modo SQLCMD**</span><span class="sxs-lookup"><span data-stu-id="e089f-122">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="e089f-123">Marque esta caixa de seleção para abrir novas consultas no modo SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="e089f-123">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="e089f-124">Para obter mais informações sobre o modo SQLCMD, consulte [Editar scripts SQLCMD com o Editor de Consultas](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e089f-124">For more information about SQLCMD mode, see [Edit SQLCMD Scripts with Query Editor](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span>  
  
 <span data-ttu-id="e089f-125">Ao selecionar essa opção, esteja atento às seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="e089f-125">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="e089f-126">O IntelliSense está desativado no Editor de Consultas do [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e089f-126">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="e089f-127">Como o Editor de Consultas não é executado na linha de comando, você não pode passar parâmetros de linha de comando, como variáveis.</span><span class="sxs-lookup"><span data-stu-id="e089f-127">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="e089f-128">Como o Editor de Consultas não pode responder a prompts do sistema operacional, você deve ter cuidado para não executar instruções interativas.</span><span class="sxs-lookup"><span data-stu-id="e089f-128">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="e089f-129">**Restaurar Padrões**</span><span class="sxs-lookup"><span data-stu-id="e089f-129">**Reset to Default**</span></span>  
 <span data-ttu-id="e089f-130">Clique para restaurar todos os valores dessa página aos seus valores padrão originais.</span><span class="sxs-lookup"><span data-stu-id="e089f-130">Click to reset all values on this page to the original default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e089f-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e089f-131">See Also</span></span>  
 [<span data-ttu-id="e089f-132">Utilitário sqlcmd</span><span class="sxs-lookup"><span data-stu-id="e089f-132">sqlcmd Utility</span></span>](../tools/sqlcmd-utility.md)  
  
  
