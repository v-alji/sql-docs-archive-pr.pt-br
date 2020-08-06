---
title: Execução de opções de consulta (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.general.f1
ms.assetid: 858a0263-2f04-4692-b8bf-63e93c998ead
author: rothja
ms.author: jroth
ms.openlocfilehash: ce3848b51b81f111333ba0e9ac12c96432dd9863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582115"
---
# <a name="query-options-execution-general-page"></a><span data-ttu-id="6fabd-102">Execução de Opções de Consultas (página Geral)</span><span class="sxs-lookup"><span data-stu-id="6fabd-102">Query Options Execution (General Page)</span></span>
  <span data-ttu-id="6fabd-103">Use essa página a fim de especificar as opções para executar consultas do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6fabd-103">Use this page to specify the options for running [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="6fabd-104">Para acessar essa caixa de diálogo, clique com o botão direito do mouse no corpo de uma janela do Editor de Consultas e clique em **Opções de Consultas**.</span><span class="sxs-lookup"><span data-stu-id="6fabd-104">To access this dialog box, right-click the body of a Query Editor window, and then click **Query Options**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="6fabd-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="6fabd-105">UI element list</span></span>  
 <span data-ttu-id="6fabd-106">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="6fabd-106">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="6fabd-107">O valor padrão 0 indica que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] esperará por resultados até que todos os resultados tenham sido recebidos.</span><span class="sxs-lookup"><span data-stu-id="6fabd-107">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="6fabd-108">Forneça um valor maior que 0 se desejar que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pare a consulta após obter o número especificado de linhas.</span><span class="sxs-lookup"><span data-stu-id="6fabd-108">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="6fabd-109">Para desligar essa opção (de forma que todas as linhas sejam retornadas), especifique SET ROWCOUNT 0.</span><span class="sxs-lookup"><span data-stu-id="6fabd-109">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="6fabd-110">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="6fabd-110">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="6fabd-111">O valor padrão de 2.147.483.647 bytes indica que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fornecerá um campo de dados completo até o limite dos campos de dados `text`, `ntext`, `nvarchar(max)` e `varchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="6fabd-111">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide a complete data field up to the limit of `text`, `ntext`, `nvarchar(max)`, and `varchar(max)` data fields.</span></span> <span data-ttu-id="6fabd-112">Não afeta o tipo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="6fabd-112">It does not affect the XML data type.</span></span> <span data-ttu-id="6fabd-113">Forneça um número menor para limitar os resultados no caso de valores grandes.</span><span class="sxs-lookup"><span data-stu-id="6fabd-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="6fabd-114">Colunas maiores que o número fornecido serão truncadas.</span><span class="sxs-lookup"><span data-stu-id="6fabd-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="6fabd-115">**Tempo limite de execução**</span><span class="sxs-lookup"><span data-stu-id="6fabd-115">**Execution time-out**</span></span>  
 <span data-ttu-id="6fabd-116">Indica o número de segundos para aguardar antes de cancelar a consulta.</span><span class="sxs-lookup"><span data-stu-id="6fabd-116">Indicates the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="6fabd-117">Um valor 0 indica uma espera infinita ou nenhum tempo limite.</span><span class="sxs-lookup"><span data-stu-id="6fabd-117">A value of 0 indicates an infinite wait, or no time-out.</span></span>  
  
 <span data-ttu-id="6fabd-118">**Separador de lotes**</span><span class="sxs-lookup"><span data-stu-id="6fabd-118">**Batch separator**</span></span>  
 <span data-ttu-id="6fabd-119">Digite uma palavra que você usa para separar instruções Transact-SQL em lotes.</span><span class="sxs-lookup"><span data-stu-id="6fabd-119">Type a word that you use to separate Transact-SQL statements into batches.</span></span> <span data-ttu-id="6fabd-120">O padrão é GO.</span><span class="sxs-lookup"><span data-stu-id="6fabd-120">The default is GO.</span></span>  
  
 <span data-ttu-id="6fabd-121">**Por padrão, abra consultas novas no Modo SQLCMD**</span><span class="sxs-lookup"><span data-stu-id="6fabd-121">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="6fabd-122">Marque esta caixa de seleção para abrir novas consultas no modo SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="6fabd-122">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="6fabd-123">Essa caixa de seleção só fica visível quando a caixa de diálogo é aberta por meio do menu **ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="6fabd-123">This check box is visible only when the dialog box is opened through the **Tools** menu.</span></span>  
  
 <span data-ttu-id="6fabd-124">Ao selecionar essa opção, esteja atento às seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="6fabd-124">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="6fabd-125">O IntelliSense está desativado no Editor de Consultas do [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6fabd-125">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="6fabd-126">Como o Editor de Consultas não é executado na linha de comando, você não pode passar parâmetros de linha de comando, como variáveis.</span><span class="sxs-lookup"><span data-stu-id="6fabd-126">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="6fabd-127">Como o Editor de Consultas não pode responder a prompts do sistema operacional, você deve ter cuidado para não executar instruções interativas.</span><span class="sxs-lookup"><span data-stu-id="6fabd-127">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="6fabd-128">**Restaurar Padrões**</span><span class="sxs-lookup"><span data-stu-id="6fabd-128">**Reset to Default**</span></span>  
 <span data-ttu-id="6fabd-129">Redefine todos os valores dessa página com os valores padrão originais.</span><span class="sxs-lookup"><span data-stu-id="6fabd-129">Resets all values on this page to the original default values.</span></span>  
  
  
