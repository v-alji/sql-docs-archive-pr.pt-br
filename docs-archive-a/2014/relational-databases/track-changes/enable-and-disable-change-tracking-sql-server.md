---
title: Habilitar e desabilitar o controle de alterações (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], disabling
- data changes [SQL Server]
- change tracking [SQL Server], enabling
- tracking data changes [SQL Server]
- change tracking [SQL Server], configuring
- data [SQL Server], changing
ms.assetid: 1c92ec7e-ae53-4498-8bfd-c66a42a24d54
author: rothja
ms.author: jroth
ms.openlocfilehash: 402c63ae03df14e3a725fbc440575f5233d502f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572957"
---
# <a name="enable-and-disable-change-tracking-sql-server"></a><span data-ttu-id="876bf-102">Habilitar e desabilitar o controle de alterações (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="876bf-102">Enable and Disable Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="876bf-103">Este tópico descreve como habilitar e desabilitar o controle de alterações para um banco de dados e uma tabela.</span><span class="sxs-lookup"><span data-stu-id="876bf-103">This topic describes how to enable and disable change tracking for a database and a table.</span></span>  
  
## <a name="enable-change-tracking-for-a-database"></a><span data-ttu-id="876bf-104">Habilitar o controle de alterações para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="876bf-104">Enable Change Tracking for a Database</span></span>  
 <span data-ttu-id="876bf-105">Antes de usar o controle de alterações, você deve habilitar o controle de alterações no nível de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="876bf-105">Before you can use change tracking, you must enable change tracking at the database level.</span></span> <span data-ttu-id="876bf-106">O exemplo a seguir mostra como habilitar o controle de alterações usando [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="876bf-106">The following example shows how to enable change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = ON  
(CHANGE_RETENTION = 2 DAYS, AUTO_CLEANUP = ON)  
```  
  
 <span data-ttu-id="876bf-107">Você também pode habilitar o controle de alterações no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usando a caixa de diálogo [Propriedades do Banco de Dados &#40;Página Controle de Alterações&#41;](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="876bf-107">You can also enable change tracking in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="876bf-108">Você pode especificar as opções CHANGE_RETENTION e AUTO_CLEANUP quando habilitar o controle de alterações e alterar os valores a qualquer momento depois que o controle de alterações estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="876bf-108">You can specify the CHANGE_RETENTION and AUTO_CLEANUP options when you enable change tracking, and you can change the values at any time after change tracking is enabled.</span></span>  
  
 <span data-ttu-id="876bf-109">O valor de retenção determina o período de tempo que o controle de alterações mantém as informações.</span><span class="sxs-lookup"><span data-stu-id="876bf-109">The change retention value specifies the time period for which change tracking information is kept.</span></span> <span data-ttu-id="876bf-110">Informações do controle de alterações anteriores a esse período de tempo são removidas periodicamente.</span><span class="sxs-lookup"><span data-stu-id="876bf-110">Change tracking information that is older than this time period is removed periodically.</span></span> <span data-ttu-id="876bf-111">Quando estiver definindo esse valor, deverá considerar com que frequência os aplicativos serão sincronizados com as tabelas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="876bf-111">When you are setting this value, you should consider how often applications will synchronize with the tables in the database.</span></span> <span data-ttu-id="876bf-112">O período de retenção especificado deve ter pelo menos a duração do período de tempo máximo entre as sincronizações.</span><span class="sxs-lookup"><span data-stu-id="876bf-112">The specified retention period must be at least as long as the maximum time period between synchronizations.</span></span> <span data-ttu-id="876bf-113">Se um aplicativo obtém as alterações em intervalos maiores, os resultados retornados podem ser incorretos porque algumas informações de alterações podem ter sido removidas.</span><span class="sxs-lookup"><span data-stu-id="876bf-113">If an application obtains changes at longer intervals, the results that are returned might be incorrect because some of the change information has probably been removed.</span></span> <span data-ttu-id="876bf-114">Para evitar resultados incorretos, um aplicativo pode usar a função de sistema CHANGE_TRACKING_MIN_VALID_VERSION para determinar se o intervalo entre as sincronizações foi muito longo.</span><span class="sxs-lookup"><span data-stu-id="876bf-114">To avoid obtaining incorrect results, an application can use the CHANGE_TRACKING_MIN_VALID_VERSION system function to determine whether the interval between synchronizations has been too long.</span></span>  
  
 <span data-ttu-id="876bf-115">Use a opção AUTO_CLEANUP para habilitar ou desabilitar a tarefa de limpeza que remove informações antigas de controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="876bf-115">You can use the AUTO_CLEANUP option to enable or disable the cleanup task that removes old change tracking information.</span></span> <span data-ttu-id="876bf-116">Isso pode ser útil quando há um problema temporário que impede os aplicativos de sincronizarem e o processo para remover as informações do controle de alterações anterior ao período de retenção precisa ser interrompido até que o problema seja resolvido.</span><span class="sxs-lookup"><span data-stu-id="876bf-116">This can be useful when there is a temporary problem that prevents applications from synchronizing and the process for removing change tracking information older than the retention period must be paused until the problem is resolved.</span></span>  
  
 <span data-ttu-id="876bf-117">Para qualquer banco de dados que use o controle de alterações, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="876bf-117">For any database that uses change tracking, be aware of the following:</span></span>  
  
-   <span data-ttu-id="876bf-118">Para usar o controle de alterações, o nível de compatibilidade do banco de dados deve ser definido como 90 ou mais.</span><span class="sxs-lookup"><span data-stu-id="876bf-118">To use change tracking, the database compatibility level must be set to 90 or greater.</span></span> <span data-ttu-id="876bf-119">Se o nível de compatibilidade de um banco de dados for inferior a 90, você poderá configurar o controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="876bf-119">If a database has a compatibility level of less than 90, you can configure change tracking.</span></span> <span data-ttu-id="876bf-120">No entanto, a função CHANGETABLE, usada para obter informações do controle de alterações, retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="876bf-120">However, the CHANGETABLE function, which is used to obtain change tracking information, will return an error.</span></span>  
  
-   <span data-ttu-id="876bf-121">Usar o isolamento do instantâneo é o modo mais fácil de garantir que todas as informações do controle de alterações sejam consistentes.</span><span class="sxs-lookup"><span data-stu-id="876bf-121">Using snapshot isolation is the easiest way for you to help ensure that all change tracking information is consistent.</span></span> <span data-ttu-id="876bf-122">Por esse motivo, é estritamente recomendável que o isolamento do instantâneo seja definido como ON para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="876bf-122">For this reason, we strongly recommend that snapshot isolation be set to ON for the database.</span></span> <span data-ttu-id="876bf-123">Para obter mais informações, veja [Trabalhar com o controle de alterações &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="876bf-123">For more information, see [Work with Change Tracking &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span></span>  
  
## <a name="enable-change-tracking-for-a-table"></a><span data-ttu-id="876bf-124">Habilitar o controle de alterações para uma tabela</span><span class="sxs-lookup"><span data-stu-id="876bf-124">Enable Change Tracking for a Table</span></span>  
 <span data-ttu-id="876bf-125">O controle de alterações deve ser habilitado para cada tabela que você deseja controlar.</span><span class="sxs-lookup"><span data-stu-id="876bf-125">Change tracking must be enabled for each table that you want tracked.</span></span> <span data-ttu-id="876bf-126">Quando o controle de alterações está habilitado, são mantidas informações sobre todas as linhas da tabela afetadas por uma operação DML.</span><span class="sxs-lookup"><span data-stu-id="876bf-126">When change tracking is enabled, change tracking information is maintained for all rows in the table that are affected by a DML operation.</span></span>  
  
 <span data-ttu-id="876bf-127">O exemplo a seguir mostra como habilitar o controle de alterações para uma tabela usando [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="876bf-127">The following example shows how to enable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
ENABLE CHANGE_TRACKING  
WITH (TRACK_COLUMNS_UPDATED = ON)  
```  
  
 <span data-ttu-id="876bf-128">Você também pode habilitar o controle de alterações para uma tabela no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usando a caixa de diálogo [Propriedades do Banco de Dados &#40;Página Controle de Alterações&#41;](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="876bf-128">You can also enable change tracking for a table in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="876bf-129">Quando a opção TRACK_COLUMNS_UPDATED é definida como ON, o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] armazena informações extras sobre quais colunas foram atualizadas na tabela interna de controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="876bf-129">When the TRACK_COLUMNS_UPDATED option is set to ON, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] stores extra information about which columns were updated to the internal change tracking table.</span></span> <span data-ttu-id="876bf-130">O controle de coluna pode permitir a um aplicativo sincronizar apenas as colunas que foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="876bf-130">Column tracking can enable an application to synchronize only those columns that were updated.</span></span> <span data-ttu-id="876bf-131">Isso pode melhorar a eficiência e o desempenho.</span><span class="sxs-lookup"><span data-stu-id="876bf-131">This can improve efficiency and performance.</span></span> <span data-ttu-id="876bf-132">Entretanto, como a manutenção de informações do controle de alterações aumenta a sobrecarga de armazenamento, essa opção é definida como OFF por padrão.</span><span class="sxs-lookup"><span data-stu-id="876bf-132">However, because maintaining column tracking information adds some extra storage overhead, this option is set to OFF by default.</span></span>  
  
## <a name="disable-change-tracking-for-a-database-or-table"></a><span data-ttu-id="876bf-133">Desabilitar o controle de alterações para um banco de dados ou uma tabela</span><span class="sxs-lookup"><span data-stu-id="876bf-133">Disable Change Tracking for a Database or Table</span></span>  
 <span data-ttu-id="876bf-134">É necessário desabilitar o controle de alterações em todas as tabelas com alterações controladas, antes que o controle de alterações seja definido como OFF no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="876bf-134">Change tracking must first be disabled for all change-tracked tables before change tracking can be set to OFF for the database.</span></span> <span data-ttu-id="876bf-135">Para determinar as tabelas que tenham o controle de alterações habilitadas em um banco de dados, use a exibição do catálogo [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) .</span><span class="sxs-lookup"><span data-stu-id="876bf-135">To determine the tables that have change tracking enabled for a database, use the [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) catalog view.</span></span>  
  
 <span data-ttu-id="876bf-136">Quando nenhuma tabela de um banco de dados controlar as alterações, você pode desabilitar o controle de alterações no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="876bf-136">When no tables in a database track changes, you can disable change tracking for the database.</span></span> <span data-ttu-id="876bf-137">O exemplo a seguir mostra como desabilitar o controle de alterações para um banco de dados usando [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="876bf-137">The following example shows how to disable change tracking for a database by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = OFF  
```  
  
 <span data-ttu-id="876bf-138">O exemplo a seguir mostra como desabilitar o controle de alterações para uma tabela usando [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="876bf-138">The following example shows how to disable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
DISABLE CHANGE_TRACKING;  
```  
  
## <a name="see-also"></a><span data-ttu-id="876bf-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="876bf-139">See Also</span></span>  
 <span data-ttu-id="876bf-140">[Propriedades do Banco de Dados &#40;Página Controle de Alterações&#41;](../databases/database-properties-changetracking-page.md) </span><span class="sxs-lookup"><span data-stu-id="876bf-140">[Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) </span></span>  
 <span data-ttu-id="876bf-141">[Opções ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="876bf-141">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="876bf-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span><span class="sxs-lookup"><span data-stu-id="876bf-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span></span>  
 <span data-ttu-id="876bf-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span><span class="sxs-lookup"><span data-stu-id="876bf-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span></span>  
 <span data-ttu-id="876bf-144">[Controle de alterações de dados &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="876bf-144">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="876bf-145">[Sobre o controle de alterações &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="876bf-145">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="876bf-146">[Trabalhar com dados de alterações &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="876bf-146">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="876bf-147">Gerenciar o controle de alterações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="876bf-147">Manage Change Tracking &#40;SQL Server&#41;</span></span>](manage-change-tracking-sql-server.md)  
  
  
