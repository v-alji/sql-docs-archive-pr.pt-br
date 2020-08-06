---
title: Exibir propriedades de chave estrangeira | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], attributes
- displaying foreign keys attributes
- viewing foreign keys attributes
ms.assetid: b0e57cb7-9b26-4b96-b76a-1f59f5f498c5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5860a0cf26b983d75bab86862ee1e5fdd7737712
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569840"
---
# <a name="view-foreign-key-properties"></a><span data-ttu-id="8baea-102">Exibir propriedades de chave estrangeira</span><span class="sxs-lookup"><span data-stu-id="8baea-102">View Foreign Key Properties</span></span>
  <span data-ttu-id="8baea-103">Você pode exibir atributos da chave estrangeira de uma relação no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8baea-103">You can view the foreign key attributes of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8baea-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8baea-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8baea-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8baea-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8baea-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="8baea-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8baea-107">**Para exibir os atributos de chave estrangeira de uma tabela específica, usando:**</span><span class="sxs-lookup"><span data-stu-id="8baea-107">**To view the foreign key attributes of a specific table, using:**</span></span>  
  
     [<span data-ttu-id="8baea-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8baea-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8baea-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8baea-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8baea-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8baea-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8baea-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="8baea-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8baea-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="8baea-112">Permissions</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="8baea-113">Para obter mais informações, consulte [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="8baea-113">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8baea-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8baea-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a><span data-ttu-id="8baea-115">Para exibir os atributos de chave estrangeira de uma relação em uma tabela específica</span><span class="sxs-lookup"><span data-stu-id="8baea-115">To view the foreign key attributes of a relationship in a specific table</span></span>  
  
1.  <span data-ttu-id="8baea-116">Abra o Designer de Tabela da tabela que contém a chave estrangeira a ser exibida, clique com o botão direito do mouse no Designer de Tabela e selecione **Relações** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="8baea-116">Open the Table Designer for the table containing the foreign key you want to view, right-click in the Table Designer, and choose **Relationships** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="8baea-117">Na caixa de diálogo **Relações de Chaves Estrangeiras** , selecione a relação com as propriedades que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="8baea-117">In the **Foreign Key Relationships** dialog box, select the relationship with properties you want to view.</span></span>  
  
 <span data-ttu-id="8baea-118">Se as colunas de chave estrangeira estiverem relacionadas a uma chave primária, as colunas de chave primária serão identificadas no **Designer de Tabela** por um símbolo de chave primária no seletor de linhas.</span><span class="sxs-lookup"><span data-stu-id="8baea-118">If the foreign key columns are related to a primary key, the primary key columns are identified in **Table Designer** by a primary key symbol in the row selector.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8baea-119">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8baea-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a><span data-ttu-id="8baea-120">Para exibir os atributos de chave estrangeira de uma relação em uma tabela específica</span><span class="sxs-lookup"><span data-stu-id="8baea-120">To view the foreign key attributes of a relationship in a specific table</span></span>  
  
1.  <span data-ttu-id="8baea-121">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8baea-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8baea-122">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8baea-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8baea-123">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8baea-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8baea-124">O exemplo retorna todas as chaves estrangeiras e suas propriedades para a tabela `HumanResources.Employee` no banco de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="8baea-124">The example returns all foreign keys and their properties for the table `HumanResources.Employee` in the sample database.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT   
        f.name AS foreign_key_name  
       ,OBJECT_NAME(f.parent_object_id) AS table_name  
       ,COL_NAME(fc.parent_object_id, fc.parent_column_id) AS constraint_column_name  
       ,OBJECT_NAME (f.referenced_object_id) AS referenced_object  
       ,COL_NAME(fc.referenced_object_id, fc.referenced_column_id) AS referenced_column_name  
       ,is_disabled  
       ,delete_referential_action_desc  
       ,update_referential_action_desc  
    FROM sys.foreign_keys AS f  
    INNER JOIN sys.foreign_key_columns AS fc   
       ON f.object_id = fc.constraint_object_id   
    WHERE f.parent_object_id = OBJECT_ID('HumanResources.Employee');  
    ```  
  
 <span data-ttu-id="8baea-125">Para obter mais informações, veja [sys.foreign_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) e [sys.foreign_key_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8baea-125">For more information, see [sys.foreign_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) and [sys.foreign_key_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
