---
title: Solução de problemas do IntelliSense
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- unavailable options [IntelliSense]
- IntelliSense [SQL Server], troubleshooting
- IntelliSense [SQL Server], unavailable options
- troubleshooting [IntelliSense]
ms.assetid: 4b72ffc6-aea2-4e11-ab36-fa2de4d7bcc5
author: rothja
ms.author: jroth
ms.openlocfilehash: 087baf616fc215c480ae78621623cbe1ed512b57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681521"
---
# <a name="troubleshooting-intellisense-sql-server-management-studio"></a><span data-ttu-id="c4f0c-102">Solucionando problemas do IntelliSense (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c4f0c-102">Troubleshooting IntelliSense (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c4f0c-103">Em certos casos, o funcionamento das opções do IntelliSense podem não ser o esperado:</span><span class="sxs-lookup"><span data-stu-id="c4f0c-103">There are certain cases when the IntelliSense options might not work as you expect.</span></span>  
  
## <a name="conditions-that-affect-intellisense"></a><span data-ttu-id="c4f0c-104">Condições que afetam o IntelliSense</span><span class="sxs-lookup"><span data-stu-id="c4f0c-104">Conditions That Affect IntelliSense</span></span>  
 <span data-ttu-id="c4f0c-105">As seguintes condições podem afetar o comportamento do IntelliSense:</span><span class="sxs-lookup"><span data-stu-id="c4f0c-105">The following conditions might affect the behavior of IntelliSense:</span></span>  
  
-   <span data-ttu-id="c4f0c-106">Há um erro de código acima do cursor.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-106">There is a code error above the cursor.</span></span>  
  
     <span data-ttu-id="c4f0c-107">Se houver uma instrução incompleta ou outro erro de código acima do local do ponto de inserção, o IntelliSense talvez não consiga analisar os elementos do código e por isso não funcionará.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-107">If there is an incomplete statement or other coding error above the location of the insertion point, IntelliSense may be unable to parse the code elements, and therefore will not work.</span></span> <span data-ttu-id="c4f0c-108">Você pode comentar o código aplicável para habilitar o IntelliSense novamente.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-108">You can comment out the applicable code to enable IntelliSense again.</span></span>  
  
-   <span data-ttu-id="c4f0c-109">O ponto de inserção está dentro de um comentário de código.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-109">The insertion point is inside a code comment.</span></span>  
  
     <span data-ttu-id="c4f0c-110">As opções do IntelliSense não são disponibilizadas quando o ponto de inserção está dentro de um comentário no arquivo de origem.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-110">IntelliSense options are not available when the insertion point is within a comment in your source file.</span></span>  
  
-   <span data-ttu-id="c4f0c-111">O ponto de inserção está dentro de uma literal da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-111">The insertion point is inside a string literal.</span></span>  
  
     <span data-ttu-id="c4f0c-112">As opções do IntelliSense não serão disponibilizadas quando o ponto de inserção estiver entre as aspas que envolvem uma literal de cadeia de caracteres, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4f0c-112">IntelliSense options are not available when the insertion point is inside the quotation marks around a string literal, for example:</span></span>  
  
     `WHERE FirstName LIKE 'Patri%|'`  
  
-   <span data-ttu-id="c4f0c-113">As opções automáticas estão desativadas.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-113">The automatic options are turned off.</span></span>  
  
     <span data-ttu-id="c4f0c-114">Muitos recursos do IntelliSense funcionam automaticamente por padrão, mas qualquer recurso pode ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-114">Many IntelliSense features work automatically by default, but you can disable any feature.</span></span>  
  
     <span data-ttu-id="c4f0c-115">Mesmo quando a conclusão automática da instrução está desabilitada, é possível usar um recurso do IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-115">Even when automatic statement completion is disabled, you can use an IntelliSense feature.</span></span> <span data-ttu-id="c4f0c-116">Para obter mais informações, consulte [Configurar IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="c4f0c-116">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
## <a name="database-engine-query-intellisense"></a><span data-ttu-id="c4f0c-117">Consulta do Mecanismo de Banco de Dados do IntelliSense</span><span class="sxs-lookup"><span data-stu-id="c4f0c-117">Database Engine Query IntelliSense</span></span>  
 <span data-ttu-id="c4f0c-118">As questões a seguir se aplicam ao Editor de Consultas [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c4f0c-118">The following issues apply to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor:</span></span>  
  
-   <span data-ttu-id="c4f0c-119">A funcionalidade IntelliSense do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] não dá suporte para todos os elementos de sintaxe do [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4f0c-119">The IntelliSense functionality of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="c4f0c-120">A ajuda do parâmetro não dá suporte para os parâmetros em alguns objetos, como procedimentos armazenados estendidos.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-120">Parameter help does not support the parameters in some objects, such as extended stored procedures.</span></span> <span data-ttu-id="c4f0c-121">Para obter mais informações, consulte [Sintaxe Transact-SQL com suporte do IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="c4f0c-121">For more information, see [Transact-SQL Syntax Supported by IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span></span>  
  
-   <span data-ttu-id="c4f0c-122">O IntelliSense está disponível apenas quando o Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] está conectado a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou posterior.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-122">IntelliSense is only available when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor is connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="c4f0c-123">O IntelliSense não está disponível quando o Editor de Consultas está conectado a versões anteriores do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4f0c-123">IntelliSense is not available when the Query Editor is connected to earlier versions of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="c4f0c-124">O IntelliSense é desativado no Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] quando o modo SQLCMD está ativado.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-124">IntelliSense is turned off in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor when the SQLCMD mode is set on.</span></span>  
  
-   <span data-ttu-id="c4f0c-125">A funcionalidade do IntelliSense não abrange objetos de banco de dados criados por outra conexão depois que a janela do editor está conectada ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-125">IntelliSense functionality does not cover database objects created by another connection after your editor window connected to the database.</span></span> <span data-ttu-id="c4f0c-126">Se os objetos estiverem ausentes nos recursos do IntelliSense, como as listas de conclusão, você poderá escolher um destes três mecanismos para atualizar o cache de objetos da janela do editor:</span><span class="sxs-lookup"><span data-stu-id="c4f0c-126">If objects are missing from IntelliSense features such as completion lists, you can choose one of these three mechanisms to refresh the cache of objects for your editor window:</span></span>  
  
    -   <span data-ttu-id="c4f0c-127">Selecione o menu **Editar** , selecione **IntelliSense**e selecione **Atualizar Cache Local**.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-127">Select the **Edit** menu, select **IntelliSense**, then select **Refresh Local Cache**.</span></span>  
  
    -   <span data-ttu-id="c4f0c-128">Use as teclas de atalho CTRL+Shift+R.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-128">Use the CTRL+Shift+R keyboard shortcut.</span></span>  
  
    -   <span data-ttu-id="c4f0c-129">Desconecte a janela do editor da instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e reconecte.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-129">Disconnect your editor window from the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and reconnect.</span></span>  
  
-   <span data-ttu-id="c4f0c-130">As listas de conclusão não contêm os objetos de banco de dados para os quais você não tem permissões.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-130">Completion lists do not include database objects for which you do not have permissions.</span></span> <span data-ttu-id="c4f0c-131">O IntelliSense sinaliza as referências aos objetos para os quais você tem permissões.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-131">IntelliSense flags references to objects for which you do have permissions.</span></span> <span data-ttu-id="c4f0c-132">Por exemplo, se você abrir um script gravado por outra pessoa, as referências aos objetos para os quais essa pessoa tem permissões e você não tem serão sinalizadas como incorretas.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-132">For example, if you open a script that is written by someone else, any references to objects for which that person has permissions and you do not are flagged as incorrect.</span></span>  
  
-   <span data-ttu-id="c4f0c-133">As listas de conclusão podem deixar de funcionar se a conexão com a instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)]for desfeita.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-133">Completion lists might stop working if you lose the connection to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="c4f0c-134">Reconecte à instância.</span><span class="sxs-lookup"><span data-stu-id="c4f0c-134">Reconnect to the instance.</span></span>  
  
  
