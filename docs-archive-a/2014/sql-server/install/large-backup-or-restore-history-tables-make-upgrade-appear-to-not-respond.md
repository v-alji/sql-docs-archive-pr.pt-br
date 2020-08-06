---
title: Tabelas de histórico grandes de backup ou restauração fazem com que a atualização pareça não responder | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- backup history tables
- history tables
ms.assetid: f88d86ec-324b-4518-b6d7-1af7e7265812
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 918c20f58c00c535d8ed41d887e9671f5e821a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569826"
---
# <a name="large-backup-or-restore-history-tables-make-upgrade-appear-to-not-respond"></a><span data-ttu-id="ce269-102">Tabelas grandes de histórico de restauração ou backup fazem com que a atualização pareça não responder</span><span class="sxs-lookup"><span data-stu-id="ce269-102">Large backup or restore history tables make upgrade appear to not respond</span></span>
  <span data-ttu-id="ce269-103">No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], foram acrescentadas novas colunas a algumas tabelas de histórico de restauração e backup.</span><span class="sxs-lookup"><span data-stu-id="ce269-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], new columns were added to some of the backup and restore history tables.</span></span> <span data-ttu-id="ce269-104">Para atualizar essas tabelas, é necessário alterá-las para adicionar as novas colunas.</span><span class="sxs-lookup"><span data-stu-id="ce269-104">Upgrading these tables requires altering them to add the new columns.</span></span> <span data-ttu-id="ce269-105">Se uma ou mais tabelas tiverem um grande número de linhas, a atualização ficará parada por um tempo significativo na instrução ALTER TABLE, que é a instrução que adiciona colunas à tabela.</span><span class="sxs-lookup"><span data-stu-id="ce269-105">If one or more of these tables contains a large number of rows, the upgrade will stall for a substantial amount of time on the ALTER TABLE statement that adds columns to that table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="ce269-106">Componente</span><span class="sxs-lookup"><span data-stu-id="ce269-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="ce269-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="ce269-107">Description</span></span>  
 <span data-ttu-id="ce269-108">A atualização pode parecer parar de responder se qualquer uma das tabelas de histórico de backup ou restauração a seguir contiver um grande número de linhas:</span><span class="sxs-lookup"><span data-stu-id="ce269-108">Upgrade can appear to stop responding if any of the following backup or restore history tables contains a large number of rows:</span></span>  
  
-   <span data-ttu-id="ce269-109">**backupfile**</span><span class="sxs-lookup"><span data-stu-id="ce269-109">**backupfile**</span></span>  
  
-   <span data-ttu-id="ce269-110">**backupmediafamily**</span><span class="sxs-lookup"><span data-stu-id="ce269-110">**backupmediafamily**</span></span>  
  
-   <span data-ttu-id="ce269-111">**backupmediaset**</span><span class="sxs-lookup"><span data-stu-id="ce269-111">**backupmediaset**</span></span>  
  
-   <span data-ttu-id="ce269-112">**backupset**</span><span class="sxs-lookup"><span data-stu-id="ce269-112">**backupset**</span></span>  
  
-   <span data-ttu-id="ce269-113">**restorefile**</span><span class="sxs-lookup"><span data-stu-id="ce269-113">**restorefile**</span></span>  
  
-   <span data-ttu-id="ce269-114">**restorefilegroup**</span><span class="sxs-lookup"><span data-stu-id="ce269-114">**restorefilegroup**</span></span>  
  
-   <span data-ttu-id="ce269-115">**restorehistory**</span><span class="sxs-lookup"><span data-stu-id="ce269-115">**restorehistory**</span></span>  
  
 <span data-ttu-id="ce269-116">Se quaisquer destas tabelas tiver 10.000 linhas ou mais, o Supervisor de Atualização reportará uma falha de não conformidade.</span><span class="sxs-lookup"><span data-stu-id="ce269-116">If any of these tables has 10,000 or more rows, Upgrade Advisor reports a noncompliance failure.</span></span> <span data-ttu-id="ce269-117">Ele não informará qual tabela excede o número de linhas permitido.</span><span class="sxs-lookup"><span data-stu-id="ce269-117">It does not report which table exceeds the allowed number of rows.</span></span> <span data-ttu-id="ce269-118">A primeira tabela que exceder 10.000 linhas causará a falha.</span><span class="sxs-lookup"><span data-stu-id="ce269-118">The first table that exceeds 10,000 rows causes the failure.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="ce269-119">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="ce269-119">Corrective Action</span></span>  
 <span data-ttu-id="ce269-120">Antes de atualizar um banco de dados, recomendamos que reduza o número de linhas para 10.000 caso uma tabela tenha mais linhas do que o especificado.</span><span class="sxs-lookup"><span data-stu-id="ce269-120">Before you upgrade a database, if any of these tables exceeds 10,000 rows, we recommend that you reduce the number to less than 10,000.</span></span> <span data-ttu-id="ce269-121">Para reduzir as linhas em todas essas tabelas, você pode executar o procedimento armazenado **sp_delete_backuphistory** .</span><span class="sxs-lookup"><span data-stu-id="ce269-121">To reduce rows in all of these tables, you can run the **sp_delete_backuphistory** stored procedure.</span></span> <span data-ttu-id="ce269-122">Esse procedimento exclui as entradas de todas as tabelas de histórico de restauração e backup para grupos de backup mais antigos do que a data especificada.</span><span class="sxs-lookup"><span data-stu-id="ce269-122">This procedure deletes the entries in all of the backup and restore history tables for backup sets older than a specified date.</span></span> <span data-ttu-id="ce269-123">Para obter mais informações, consulte [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ce269-123">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce269-124">Você pode atualizar um banco de dados cujas tabelas de histórico de restauração e backup tenham mais de 10.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="ce269-124">You can upgrade a database whose backup and restore history tables are larger than 10,000 rows.</span></span> <span data-ttu-id="ce269-125">Mas a atualização pode parecer estar parada enquanto essas tabelas grandes estiverem sendo alteradas.</span><span class="sxs-lookup"><span data-stu-id="ce269-125">But the upgrade may appear to stall while large tables are being altered.</span></span> <span data-ttu-id="ce269-126">Quanto maior a tabela, mais tempo a Instalação levará para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="ce269-126">The larger the tables, the longer that Setup takes to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce269-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ce269-127">See Also</span></span>  
 <span data-ttu-id="ce269-128">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="ce269-128">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="ce269-129">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="ce269-129">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
