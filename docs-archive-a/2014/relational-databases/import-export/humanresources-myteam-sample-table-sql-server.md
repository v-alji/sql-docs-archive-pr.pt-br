---
title: Tabela de exemplo HumanResources.myTeam (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- myTeam sample table [SQL Server]
- bulk importing [SQL Server], examples
- bulk exporting [SQL Server], examples
ms.assetid: 27da45a0-c1f4-4bf4-ab24-6196e80d3834
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7d4e0cbbf42c2bdd25e3dd7c9577e4d0ec44549a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576386"
---
# <a name="humanresourcesmyteam-sample-table-sql-server"></a><span data-ttu-id="9cfb9-102">Tabela de exemplo HumanResources.myTeam (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9cfb9-102">HumanResources.myTeam Sample Table (SQL Server)</span></span>
  <span data-ttu-id="9cfb9-103">Muitos dos exemplos de código em [Importando e exportando dados em massa](bulk-import-and-export-of-data-sql-server.md) exigem uma tabela de teste com finalidade especial denominada **myTeam**.</span><span class="sxs-lookup"><span data-stu-id="9cfb9-103">Many of the code examples in [Importing and Exporting Bulk Data](bulk-import-and-export-of-data-sql-server.md) require a special-purpose test table named **myTeam**.</span></span> <span data-ttu-id="9cfb9-104">Antes de poder executar os exemplos, você deve criar a tabela **myTeam** no esquema **HumanResources** do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9cfb9-104">Before you can run the examples, you must create the **myTeam** table in the **HumanResources** schema of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="9cfb9-105">é um dos bancos de dados de exemplo no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cfb9-105">is one of the sample databases in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="9cfb9-106">A tabela **myTeam** contém as seguintes colunas.</span><span class="sxs-lookup"><span data-stu-id="9cfb9-106">The **myTeam** table is contains the following columns.</span></span>  
  
|<span data-ttu-id="9cfb9-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="9cfb9-107">Column</span></span>|<span data-ttu-id="9cfb9-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="9cfb9-108">Data type</span></span>|<span data-ttu-id="9cfb9-109">Nulidade</span><span class="sxs-lookup"><span data-stu-id="9cfb9-109">Nullability</span></span>|<span data-ttu-id="9cfb9-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="9cfb9-110">Description</span></span>|  
|------------|---------------|-----------------|-----------------|  
|<span data-ttu-id="9cfb9-111">**EmployeeID**</span><span class="sxs-lookup"><span data-stu-id="9cfb9-111">**EmployeeID**</span></span>|`smallint`|<span data-ttu-id="9cfb9-112">Não nulo</span><span class="sxs-lookup"><span data-stu-id="9cfb9-112">Not null</span></span>|<span data-ttu-id="9cfb9-113">Chave primária para as linhas.</span><span class="sxs-lookup"><span data-stu-id="9cfb9-113">Primary key for the rows.</span></span> <span data-ttu-id="9cfb9-114">A ID de funcionário de um membro da minha equipe.</span><span class="sxs-lookup"><span data-stu-id="9cfb9-114">Employee ID of a member of my team.</span></span>|  
|<span data-ttu-id="9cfb9-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9cfb9-115">**Name**</span></span>|`nvarchar(50)`|<span data-ttu-id="9cfb9-116">Não nulo</span><span class="sxs-lookup"><span data-stu-id="9cfb9-116">Not null</span></span>|<span data-ttu-id="9cfb9-117">Nome de um membro de myTeam.</span><span class="sxs-lookup"><span data-stu-id="9cfb9-117">Name of a member of my team.</span></span>|  
|<span data-ttu-id="9cfb9-118">**Título**</span><span class="sxs-lookup"><span data-stu-id="9cfb9-118">**Title**</span></span>|`nvarchar(50)`|<span data-ttu-id="9cfb9-119">Nullable</span><span class="sxs-lookup"><span data-stu-id="9cfb9-119">Nullable</span></span>|<span data-ttu-id="9cfb9-120">O cargo que o funcionário exerce na minha equipe.</span><span class="sxs-lookup"><span data-stu-id="9cfb9-120">Title the employee performs on my team.</span></span>|  
|<span data-ttu-id="9cfb9-121">**Informações**</span><span class="sxs-lookup"><span data-stu-id="9cfb9-121">**Background**</span></span>|`nvarchar(50)`|<span data-ttu-id="9cfb9-122">Não nulo</span><span class="sxs-lookup"><span data-stu-id="9cfb9-122">Not null</span></span>|<span data-ttu-id="9cfb9-123">Data e hora da última atualização da linha.</span><span class="sxs-lookup"><span data-stu-id="9cfb9-123">Date and time the row was last updated.</span></span> <span data-ttu-id="9cfb9-124">(Padrão)</span><span class="sxs-lookup"><span data-stu-id="9cfb9-124">(Default)</span></span>|  
  
 <span data-ttu-id="9cfb9-125">**Para criar HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="9cfb9-125">**To create HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="9cfb9-126">Use as seguintes instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="9cfb9-126">Use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    --Create HumanResources.MyTeam:   
    USE AdventureWorks;  
    GO  
    CREATE TABLE HumanResources.myTeam   
    (EmployeeID smallint NOT NULL,  
    Name nvarchar(50) NOT NULL,  
    Title nvarchar(50) NULL,  
    Background nvarchar(50) NOT NULL DEFAULT ''  
    );  
    GO  
    ```  
  
 <span data-ttu-id="9cfb9-127">**Para popular HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="9cfb9-127">**To populate HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="9cfb9-128">Execute as seguintes instruções `INSERT` para popular a tabela com duas linhas:</span><span class="sxs-lookup"><span data-stu-id="9cfb9-128">Execute following `INSERT` statements to populate the table with two rows:</span></span>  
  
    ```  
    USE AdventureWorks;  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(77,'Mia Doppleganger','Administrative Assistant','Microsoft Office');  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(49,'Hirum Mollicat','I.T. Specialist','Report Writing and Data Mining');  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="9cfb9-129">Essas instruções ignoram a quarta coluna, `Background`.</span><span class="sxs-lookup"><span data-stu-id="9cfb9-129">These statements skip the fourth column, `Background`.</span></span> <span data-ttu-id="9cfb9-130">Isso tem um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="9cfb9-130">This has a default value.</span></span> <span data-ttu-id="9cfb9-131">Ignorar essa coluna faz com que essa instrução `INSERT` deixe a coluna em branco.</span><span class="sxs-lookup"><span data-stu-id="9cfb9-131">Skipping this column causes this `INSERT` statement to leave this column blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cfb9-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9cfb9-132">See Also</span></span>  
 [<span data-ttu-id="9cfb9-133">Importação e exportação em massa de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9cfb9-133">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](bulk-import-and-export-of-data-sql-server.md)  
  
  
