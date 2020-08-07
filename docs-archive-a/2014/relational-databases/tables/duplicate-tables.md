---
title: Duplicar tabelas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- tables [SQL Server], duplicating
- duplicating tables
- table copying [SQL Server]
ms.assetid: c6b07423-d1e5-4e5e-8681-5088921f5df3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 793a38416f86a5b43a3e3bb2420127d7acf2af1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571920"
---
# <a name="duplicate-tables"></a><span data-ttu-id="8e3e8-102">Duplicar tabelas</span><span class="sxs-lookup"><span data-stu-id="8e3e8-102">Duplicate Tables</span></span>
  <span data-ttu-id="8e3e8-103">Você pode duplicar uma tabela existente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] criando uma nova tabela e copiando as informações de coluna de uma tabela existente.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-103">You can duplicate an existing table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] by creating a new table and then copying column information from an existing table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e3e8-104">Essa operação duplica apenas a estrutura de uma tabela; ela não duplica nenhuma linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-104">This operation duplicates only the structure of a table; it does not duplicate any table rows.</span></span>  
  
 <span data-ttu-id="8e3e8-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8e3e8-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8e3e8-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8e3e8-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8e3e8-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="8e3e8-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8e3e8-108">**Para duplicar uma tabela usando:**</span><span class="sxs-lookup"><span data-stu-id="8e3e8-108">**To duplicate a table, using:**</span></span>  
  
     [<span data-ttu-id="8e3e8-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e3e8-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8e3e8-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8e3e8-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8e3e8-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8e3e8-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8e3e8-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="8e3e8-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8e3e8-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="8e3e8-113">Permissions</span></span>  
 <span data-ttu-id="8e3e8-114">Exige permissão CREATE DATABASE no banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-114">Requires CREATE TABLE permission in the destination database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8e3e8-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e3e8-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-duplicate-a-table"></a><span data-ttu-id="8e3e8-116">Para duplicar uma tabela</span><span class="sxs-lookup"><span data-stu-id="8e3e8-116">To duplicate a table</span></span>  
  
1.  <span data-ttu-id="8e3e8-117">Verifique se você está conectado ao banco de dados em que deseja criar a tabela e se o banco de dados está selecionado no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-117">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="8e3e8-118">No Pesquisador de Objetos, clique com o botão direito do mouse em **Tabelas** e clique em **Nova Tabela**.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-118">In Object Explorer, right-click **Tables** and click **New Table**.</span></span>  
  
3.  <span data-ttu-id="8e3e8-119">No Pesquisador de Objetos, clique com o botão direito do mouse na tabela que deseja copiar e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-119">In Object Explorer right-click the table you want to copy and click **Design**.</span></span>  
  
4.  <span data-ttu-id="8e3e8-120">Selecione as colunas na tabela existente e, no menu **Editar** , clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-120">Select the columns in the existing table and, from the **Edit** menu, click **Copy**.</span></span>  
  
5.  <span data-ttu-id="8e3e8-121">Volte para a nova tabela nova e selecione a primeira linha.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-121">Switch back to the new table and select the first row.</span></span>  
  
6.  <span data-ttu-id="8e3e8-122">No menu **Editar** , clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-122">From the **Edit** menu, click **Paste**.</span></span>  
  
7.  <span data-ttu-id="8e3e8-123">No menu **Arquivo** , clique em **Salvar**_table name_.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-123">From the **File** menu, click **Save**_table name_.</span></span>  
  
8.  <span data-ttu-id="8e3e8-124">Na caixa de diálogo **Escolher Nome** , digite um nome para a nova tabela e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-124">In the **Choose Name** dialog box, type a name for the new table and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8e3e8-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8e3e8-125">Using Transact-SQL</span></span>  
  
#### <a name="to-duplicate-a-table-in-query-editor"></a><span data-ttu-id="8e3e8-126">Para duplicar uma tabela no Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="8e3e8-126">To duplicate a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="8e3e8-127">Verifique se você está conectado ao banco de dados em que deseja criar a tabela e se o banco de dados está selecionado no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-127">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="8e3e8-128">Clique com o botão direito do mouse na tabela que você deseja duplicar, aponte para **Gerar Script de Tabela como**e para **CREATE to**e selecione **Nova Janela do Editor de Consultas**.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-128">Right-click the table you wish to duplicate, point to **Script Table as**, then point to **CREATE to**, and then select **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="8e3e8-129">Altere o nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-129">Change the name of the table.</span></span>  
  
4.  <span data-ttu-id="8e3e8-130">Remova as colunas que não são necessárias na nova tabela.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-130">Remove any columns that are not needed in the new table.</span></span>  
  
5.  <span data-ttu-id="8e3e8-131">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8e3e8-131">Click **Execute**.</span></span>  
  
  
