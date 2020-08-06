---
title: Criar sinônimos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
f1_keywords:
- sql12.swb.synonym.general.f1
helpviewer_keywords:
- creating synonyms
- synonyms [SQL Server], creating
ms.assetid: fedfa7a5-d0b6-4e2b-90f4-a08122958e33
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dc18c9d0d6048c4190ba56725dd332f2dfb629e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568406"
---
# <a name="create-synonyms"></a><span data-ttu-id="3b646-102">Criar sinônimos</span><span class="sxs-lookup"><span data-stu-id="3b646-102">Create Synonyms</span></span>
  <span data-ttu-id="3b646-103">Este tópico descreve como criar um sinônimo no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b646-103">This topic describes how to create a synonym in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3b646-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="3b646-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3b646-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="3b646-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3b646-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="3b646-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3b646-107">**Para criar um sinônimo, usando:**</span><span class="sxs-lookup"><span data-stu-id="3b646-107">**To create a synonym, using:**</span></span>  
  
     [<span data-ttu-id="3b646-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3b646-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3b646-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3b646-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3b646-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3b646-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3b646-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="3b646-111">Security</span></span>  
 <span data-ttu-id="3b646-112">Para criar um sinônimo em um determinado esquema, o usuário deve ter a permissão CREATE SYNONYM e ou ser proprietário do esquema ou ter a permissão ALTER SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="3b646-112">To create a synonym in a given schema, a user must have CREATE SYNONYM permission and either own the schema or have ALTER SCHEMA permission.</span></span> <span data-ttu-id="3b646-113">A permissão CREATE SYNONYM pode ser concedida.</span><span class="sxs-lookup"><span data-stu-id="3b646-113">The CREATE SYNONYM permission is a grantable permission.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3b646-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="3b646-114">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3b646-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3b646-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="3b646-116">Para criar um sinônimo</span><span class="sxs-lookup"><span data-stu-id="3b646-116">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="3b646-117">No **Pesquisador de Objetos**, expanda o banco de dados em que você deseja criar a nova exibição.</span><span class="sxs-lookup"><span data-stu-id="3b646-117">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="3b646-118">Clique com o botão direito do mouse na pasta **Sinônimos** e clique em **Novo Sinônimo...** .</span><span class="sxs-lookup"><span data-stu-id="3b646-118">Right-click the **Synonyms** folder, then click **New Synonym...**.</span></span>  
  
3.  <span data-ttu-id="3b646-119">Na caixa de diálogo **Adicionar Sinônimo** , insira as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="3b646-119">In the **Add Synonym** dialog box, enter the following information.</span></span>  
  
     <span data-ttu-id="3b646-120">**Nome de sinônimo**</span><span class="sxs-lookup"><span data-stu-id="3b646-120">**Synonym name**</span></span>  
     <span data-ttu-id="3b646-121">Digite o nome novo que você usará para esse objeto.</span><span class="sxs-lookup"><span data-stu-id="3b646-121">Type the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="3b646-122">**Esquema de sinônimo**</span><span class="sxs-lookup"><span data-stu-id="3b646-122">**Synonym schema**</span></span>  
     <span data-ttu-id="3b646-123">Digite o esquema do nome novo que você usará para esse objeto.</span><span class="sxs-lookup"><span data-stu-id="3b646-123">Type the schema of the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="3b646-124">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="3b646-124">**Server name**</span></span>  
     <span data-ttu-id="3b646-125">Digite a instância do servidor para conectar.</span><span class="sxs-lookup"><span data-stu-id="3b646-125">Type the server instance to connect to.</span></span>  
  
     <span data-ttu-id="3b646-126">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="3b646-126">**Database name**</span></span>  
     <span data-ttu-id="3b646-127">Digite ou selecione o banco de dados que contém o objeto.</span><span class="sxs-lookup"><span data-stu-id="3b646-127">Type or select the database containing the object.</span></span>  
  
     <span data-ttu-id="3b646-128">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="3b646-128">**Schema**</span></span>  
     <span data-ttu-id="3b646-129">Digite ou selecione o esquema que possui o objeto.</span><span class="sxs-lookup"><span data-stu-id="3b646-129">Type or select the schema that owns the object.</span></span>  
  
     <span data-ttu-id="3b646-130">**Tipo de objeto**</span><span class="sxs-lookup"><span data-stu-id="3b646-130">**Object type**</span></span>  
     <span data-ttu-id="3b646-131">Selecione o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="3b646-131">Select the type of object.</span></span>  
  
     <span data-ttu-id="3b646-132">**Nome do objeto**</span><span class="sxs-lookup"><span data-stu-id="3b646-132">**Object name**</span></span>  
     <span data-ttu-id="3b646-133">Digite o nome do objeto ao qual se refere o sinônimo.</span><span class="sxs-lookup"><span data-stu-id="3b646-133">Type the name of the object to which the synonym refers.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3b646-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3b646-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="3b646-135">Para criar um sinônimo</span><span class="sxs-lookup"><span data-stu-id="3b646-135">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="3b646-136">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b646-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3b646-137">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3b646-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3b646-138">Copie e cole os exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3b646-138">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="3b646-139">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3b646-139">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="3b646-140">O exemplo a seguir cria um sinônimo para uma tabela existente no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b646-140">The following example creates a synonym for an existing table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="3b646-141">O sinônimo é usado então em exemplos subsequentes.</span><span class="sxs-lookup"><span data-stu-id="3b646-141">The synonym is then used in subsequent examples.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyAddressType  
FOR AdventureWorks2012.Person.AddressType;  
GO  
```  
  
 <span data-ttu-id="3b646-142">O exemplo a seguir insere uma linha na tabela base que é referida pelo sinônimo `MyAddressType` .</span><span class="sxs-lookup"><span data-stu-id="3b646-142">The following example inserts a row into the base table that is referenced by the `MyAddressType` synonym.</span></span>  
  
```  
USE tempdb;  
GO  
INSERT INTO MyAddressType (Name)  
VALUES ('Test');  
GO  
```  
  
 <span data-ttu-id="3b646-143">O exemplo a seguir demonstra como um sinônimo pode ser referido no SQL dinâmico.</span><span class="sxs-lookup"><span data-stu-id="3b646-143">The following example demonstrates how a synonym can be referenced in dynamic SQL.</span></span>  
  
```  
USE tempdb;  
GO  
EXECUTE ('SELECT Name FROM MyAddressType');  
GO  
```  
  
  
