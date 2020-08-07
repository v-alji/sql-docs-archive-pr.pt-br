---
title: Exibir a definição da tabela | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- showing table properties
- displaying table properties
- tables [SQL Server], properties
- viewing table properties
ms.assetid: 1865fb7c-f480-4100-9007-df5364cd002a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53170a78a104bfce4b4e4177015461f2eb9093e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584069"
---
# <a name="view-the-table-definition"></a><span data-ttu-id="0d1b7-102">Exibir a definição da tabela</span><span class="sxs-lookup"><span data-stu-id="0d1b7-102">View the Table Definition</span></span>
  <span data-ttu-id="0d1b7-103">Você pode exibir as propriedades de uma tabela no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d1b7-103">You can display properties for a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0d1b7-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="0d1b7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0d1b7-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="0d1b7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0d1b7-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="0d1b7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0d1b7-107">**Para exibir as propriedades da tabela usando:**</span><span class="sxs-lookup"><span data-stu-id="0d1b7-107">**To display table properties, using:**</span></span>  
  
     [<span data-ttu-id="0d1b7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0d1b7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0d1b7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0d1b7-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0d1b7-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0d1b7-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0d1b7-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="0d1b7-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0d1b7-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="0d1b7-112">Permissions</span></span>  
 <span data-ttu-id="0d1b7-113">Você poderá ver as propriedades de uma tabela somente se for proprietário da tabela ou tiver permissões concedidas para essa tabela.</span><span class="sxs-lookup"><span data-stu-id="0d1b7-113">You can only see properties in a table if you either own the table or have been granted permissions to that table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0d1b7-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0d1b7-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-table-properties-in-the-properties-window"></a><span data-ttu-id="0d1b7-115">Para mostrar as propriedades da tabela na janela Propriedades</span><span class="sxs-lookup"><span data-stu-id="0d1b7-115">To show table properties in the Properties window</span></span>  
  
1.  <span data-ttu-id="0d1b7-116">No Pesquisador de Objetos, selecione a tabela da qual deseja exibir as propriedades.</span><span class="sxs-lookup"><span data-stu-id="0d1b7-116">In Object Explorer, select the table for which you want to show properties.</span></span>  
  
2.  <span data-ttu-id="0d1b7-117">Clique com o botão direito do mouse na tabela e escolha **Propriedades** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="0d1b7-117">Right-click the table and choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="0d1b7-118">Para obter mais informações, consulte [Table Properties](table-properties-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="0d1b7-118">For more information, see [Table Properties](table-properties-ssms.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0d1b7-119">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0d1b7-119">Using Transact-SQL</span></span>  
  
#### <a name="to-show-table-properties"></a><span data-ttu-id="0d1b7-120">Para exibir as propriedades da tabela</span><span class="sxs-lookup"><span data-stu-id="0d1b7-120">To show table properties</span></span>  
  
1.  <span data-ttu-id="0d1b7-121">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d1b7-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0d1b7-122">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="0d1b7-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0d1b7-123">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="0d1b7-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0d1b7-124">O exemplo retorna todas as colunas da exibição de catálogo `sys.tables` do objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="0d1b7-124">The example returns all columns from the `sys.tables` catalog view for the specified object.</span></span>  
  
    ```  
    SELECT * FROM sys.tables  
    WHERE object_id = 1973582069;  
  
    ```  
  
 <span data-ttu-id="0d1b7-125">Para obter mais informações, consulte [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d1b7-125">For more information, see [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
