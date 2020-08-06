---
title: Modificar as estatísticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], modifying
- modifying statistics
ms.assetid: b06299ca-ed52-411a-b245-45eac4628c99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6dd44da6d1a80050f37f08e49773f95af0e5a339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582360"
---
# <a name="modify-statistics"></a><span data-ttu-id="bbb82-102">Modificar estatísticas</span><span class="sxs-lookup"><span data-stu-id="bbb82-102">Modify Statistics</span></span>
  <span data-ttu-id="bbb82-103">Você pode modificar as estatísticas existentes no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbb82-103">You can modify existing statistics in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="bbb82-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="bbb82-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bbb82-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="bbb82-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bbb82-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="bbb82-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bbb82-107">**Para modificar as estatísticas usando:**</span><span class="sxs-lookup"><span data-stu-id="bbb82-107">**To modify statistics, using:**</span></span>  
  
     [<span data-ttu-id="bbb82-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bbb82-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bbb82-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bbb82-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bbb82-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="bbb82-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bbb82-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="bbb82-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bbb82-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="bbb82-112">Permissions</span></span>  
 <span data-ttu-id="bbb82-113">Requer que:</span><span class="sxs-lookup"><span data-stu-id="bbb82-113">Requires that:</span></span>  
  
-   <span data-ttu-id="bbb82-114">O usuário tenha a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="bbb82-114">The user has ALTER permission on the table or view.</span></span>  
  
-   <span data-ttu-id="bbb82-115">O usuário como o proprietário da tabela ou exibição indexada ou um membro de uma das seguintes funções: função de servidor fixa **sysadmin** , função de banco de dados fixa **db_owner** ou a função de banco de dados fixa **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="bbb82-115">The user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bbb82-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bbb82-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-statistics"></a><span data-ttu-id="bbb82-117">Para modificar as estatísticas</span><span class="sxs-lookup"><span data-stu-id="bbb82-117">To modify statistics</span></span>  
  
1.  <span data-ttu-id="bbb82-118">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o banco de dados no qual você deseja modificar uma estatística.</span><span class="sxs-lookup"><span data-stu-id="bbb82-118">In **Object Explorer**, click the plus sign to expand the database in which you want to modify a statistic.</span></span>  
  
2.  <span data-ttu-id="bbb82-119">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="bbb82-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="bbb82-120">Clique no sinal de adição para expandir a tabela na qual você deseja modificar uma estatística.</span><span class="sxs-lookup"><span data-stu-id="bbb82-120">Click the plus sign to expand the table in which you want to modify a statistic.</span></span>  
  
4.  <span data-ttu-id="bbb82-121">Clique no sinal de adição para expandir a pasta **Estatísticas** .</span><span class="sxs-lookup"><span data-stu-id="bbb82-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="bbb82-122">Clique com o botão direito do mouse no objeto de estatísticas que você deseja modificar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="bbb82-122">Right-click the statistics object that you wish to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="bbb82-123">Na caixa de diálogo **Propriedades de Estatísticas –** *statistics_name*, na página **Geral**, clique em **Adicionar**, **Remover**, **Mover para Cima**, **Mover para Baixo**, qualquer combinação, para alterar as propriedades das estatísticas.</span><span class="sxs-lookup"><span data-stu-id="bbb82-123">In the **Statistics Properties -** *statistics_name* dialog box, on the **General** page, click **Add**, **Remove**, **Move Up**, or **Move Down**, or any combination, to alter the properties of the statistics.</span></span> <span data-ttu-id="bbb82-124">Lembre-se de que a localização de uma coluna na grade **Colunas de Estatísticas** pode afetar substancialmente a utilidade das estatísticas.</span><span class="sxs-lookup"><span data-stu-id="bbb82-124">Remember that a column's location within the **Statistics Columns** grid can substantially impact the usefulness of the statistics.</span></span>  
  
7.  <span data-ttu-id="bbb82-125">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbb82-125">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bbb82-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bbb82-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="bbb82-127">**Para modificar as estatísticas**</span><span class="sxs-lookup"><span data-stu-id="bbb82-127">**To modify statistics**</span></span>  
  
 <span data-ttu-id="bbb82-128">Esta tarefa não pode ser executada usando instruções Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="bbb82-128">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="bbb82-129">Para modificar as estatísticas usando Transact-SQL, primeiro você deve excluir a estatística existente e depois recriá-la com novos atributos.</span><span class="sxs-lookup"><span data-stu-id="bbb82-129">To modify statistics using Transact-SQL, you must first delete the existing statistic and then re-create it with new attributes.</span></span>  
  
 <span data-ttu-id="bbb82-130">Para obter mais informações, veja [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) e [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bbb82-130">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) and [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
