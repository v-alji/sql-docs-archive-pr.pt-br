---
title: Criar uma chave mestra do banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2019
ms.prod: sql-server-2014
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], creating
ms.assetid: 8cb24263-e97d-4e4d-9429-6cf494a4d5eb
author: jaszymas
ms.author: jaszymas
ms.reviewer: carlrab
ms.openlocfilehash: cb8305d9d5a3c72e6dffafd231f21110a5abdd14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685504"
---
# <a name="create-a-database-master-key"></a><span data-ttu-id="90bd9-102">Criar uma chave mestra de banco de dados</span><span class="sxs-lookup"><span data-stu-id="90bd9-102">Create a Database Master Key</span></span>

<span data-ttu-id="90bd9-103">Este tópico descreve como criar uma chave mestra de banco de dados no usando o `master` [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90bd9-103">This topic describes how to create a database master key in the `master` database in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>

<span data-ttu-id="90bd9-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="90bd9-104">**In This Topic**</span></span>

- <span data-ttu-id="90bd9-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="90bd9-105">**Before you begin:**</span></span>

  [<span data-ttu-id="90bd9-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="90bd9-106">Security</span></span>](#Security)

- [<span data-ttu-id="90bd9-107">Para criar uma chave mestra do banco de dados usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90bd9-107">To create a database master key using Transact-SQL</span></span>](#TsqlProcedure)

## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="90bd9-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="90bd9-108">Before You Begin</span></span>

### <a name="security"></a><a name="Security"></a> <span data-ttu-id="90bd9-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="90bd9-109">Security</span></span>

#### <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="90bd9-110">Permissões</span><span class="sxs-lookup"><span data-stu-id="90bd9-110">Permissions</span></span>

<span data-ttu-id="90bd9-111">Exige a permissão CONTROL no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="90bd9-111">Requires CONTROL permission on the database.</span></span>

## <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="90bd9-112">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90bd9-112">Using Transact-SQL</span></span>

### <a name="to-create-a-database-master-key"></a><span data-ttu-id="90bd9-113">Criar uma chave mestra de banco de dados</span><span class="sxs-lookup"><span data-stu-id="90bd9-113">To create a database master key</span></span>

1. <span data-ttu-id="90bd9-114">Escolha uma senha por criptografar a cópia da chave mestra que será armazenada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="90bd9-114">Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span>
2. <span data-ttu-id="90bd9-115">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90bd9-115">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>
3. <span data-ttu-id="90bd9-116">Expanda **Bancos de Dados do Sistema**, clique com o botão direito do mouse `master` e clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-116">Expand **System Databases**, right-click `master` and then click **New Query**.</span></span>
4. <span data-ttu-id="90bd9-117">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="90bd9-117">Copy and paste the following example into the query window and click **Execute**.</span></span>

  ```sql
  -- Creates the master key.
  -- The key is encrypted using the password "23987hxJ#KL95234nl0zBe."
  CREATE MASTER KEY ENCRYPTION BY PASSWORD = '23987hxJ#KL95234nl0zBe';
```

<span data-ttu-id="90bd9-118">Para obter mais informações, veja [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="90bd9-118">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql).</span></span>
