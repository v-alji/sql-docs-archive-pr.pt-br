---
title: Bancos de dados do sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system databases [SQL Server]
- displaying system database data
- modifying system data
- viewing system database data
ms.assetid: 30468a7c-4225-4d35-aa4a-ffa7da4f1282
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65deee685c2205a7c6e41ed86f71c69639555d7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678771"
---
# <a name="system-databases"></a><span data-ttu-id="d1ae1-102">Bancos de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="d1ae1-102">System Databases</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d1ae1-103">inclui os seguintes bancos de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-103">includes the following system databases.</span></span>  
  
|<span data-ttu-id="d1ae1-104">Banco de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="d1ae1-104">System database</span></span>|<span data-ttu-id="d1ae1-105">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="d1ae1-105">Description</span></span>|  
|---------------------|-----------------|  
|[<span data-ttu-id="d1ae1-106">Banco de dados mestre</span><span class="sxs-lookup"><span data-stu-id="d1ae1-106">master Database</span></span>](master-database.md)|<span data-ttu-id="d1ae1-107">Registra toda a informações de nível de sistema por uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1ae1-107">Records all the system-level information for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="d1ae1-108">Banco de dados msdb</span><span class="sxs-lookup"><span data-stu-id="d1ae1-108">msdb Database</span></span>](msdb-database.md)|<span data-ttu-id="d1ae1-109">É usado pelo SQL Server Agent para programar alertas e trabalhos.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-109">Is used by SQL Server Agent for scheduling alerts and jobs.</span></span>|  
|[<span data-ttu-id="d1ae1-110">Modelo de banco de dados</span><span class="sxs-lookup"><span data-stu-id="d1ae1-110">model Database</span></span>](model-database.md)|<span data-ttu-id="d1ae1-111">É usado como modelo de todos os bancos de dados criados na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1ae1-111">Is used as the template for all databases created on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d1ae1-112">As modificações feitas no banco de dados **modelo**, como tamanho, ordenação, modelo de recuperação, e outras opções de bancos de dados, são aplicadas a qualquer banco de dados criados em seguida.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-112">Modifications made to the **model** database, such as database size, collation, recovery model, and other database options, are applied to any databases created afterward.</span></span>|  
|[<span data-ttu-id="d1ae1-113">Banco de dados de recursos</span><span class="sxs-lookup"><span data-stu-id="d1ae1-113">Resource Database</span></span>](resource-database.md)|<span data-ttu-id="d1ae1-114">É um banco de dados do tipo somente leitura que contém objetos de sistema incluídos no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1ae1-114">Is a read-only database that contains system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d1ae1-115">Os objetos de sistema são fisicamente persistentes no banco de dados **Recurso** , mas aparecem logicamente no esquema **sys** de todo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-115">System objects are physically persisted in the **Resource** database, but they logically appear in the **sys** schema of every database.</span></span>|  
|[<span data-ttu-id="d1ae1-116">Banco de dados tempdb</span><span class="sxs-lookup"><span data-stu-id="d1ae1-116">tempdb Database</span></span>](tempdb-database.md)|<span data-ttu-id="d1ae1-117">É um workspace para reter objetos temporários ou conjuntos de resultados intermediários.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-117">Is a workspace for holding temporary objects or intermediate result sets.</span></span>|  
  
## <a name="modifying-system-data"></a><span data-ttu-id="d1ae1-118">modificando dados do sistema</span><span class="sxs-lookup"><span data-stu-id="d1ae1-118">Modifying System Data</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d1ae1-119">não oferece suporte aos usuários diretamente na atualização de informações de objetos do sistema como tabelas de sistema, procedimentos armazenados do sistema  e exibições de catálogo.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-119">does not support users directly updating the information in system objects such as system tables, system stored procedures, and catalog views.</span></span> <span data-ttu-id="d1ae1-120">Em lugar disso, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece um conjunto completo de ferramentas administrativas que permitem aos usuários administrar totalmente seus sistemas e gerenciar todos os usuários e objetos de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-120">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides a complete set of administrative tools that let users fully administer their system and manage all users and objects in a database.</span></span> <span data-ttu-id="d1ae1-121">Entre elas estão as seguintes:</span><span class="sxs-lookup"><span data-stu-id="d1ae1-121">These include the following:</span></span>  
  
-   <span data-ttu-id="d1ae1-122">Utilitários de administração, como o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1ae1-122">Administration utilities, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="d1ae1-123">SQL-SMO API.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-123">SQL-SMO API.</span></span> <span data-ttu-id="d1ae1-124">Isso permite que os programadores incluam a funcionalidade completa para administrar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-124">This lets programmers include complete functionality for administering [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in their applications.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="d1ae1-125">.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-125">scripts and stored procedures.</span></span> <span data-ttu-id="d1ae1-126">Podem usar procedimentos armazenados do sistema e instruções DDL [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1ae1-126">These can use system stored procedures and [!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statements.</span></span>  
  
 <span data-ttu-id="d1ae1-127">Essas ferramentas protegem os aplicativos das alterações nos objetos de sistema.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-127">These tools shield applications from changes in the system objects.</span></span> <span data-ttu-id="d1ae1-128">Por exemplo, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] algumas vezes precisa alterar as tabelas de sistema em novas versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para dar suporte a nova funcionalidade adicionada nessa versão.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-128">For example, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sometimes has to change the system tables in new versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to support new functionality that is being added in that version.</span></span> <span data-ttu-id="d1ae1-129">Os aplicativos que emitem instruções SELECT que diretamente referenciam tabelas do sistema são frequentemente dependentes do formato antigo das tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-129">Applications issuing SELECT statements that directly reference system tables are frequently dependent on the old format of the system tables.</span></span> <span data-ttu-id="d1ae1-130">Possivelmente, os sites só serão capazes de fazer a atualizar para uma nova versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] após regravarem os aplicativos que estão sendo selecionados nas tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-130">Sites may not be able to upgrade to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until they have rewritten applications that are selecting from system tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d1ae1-131">considera os procedimentos armazenados do sistema, a DDL e as interfaces publicadas SQL-SMO, e trabalha para manter a compatibilidade com as versões anteriores dessas interfaces.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-131">considers the system stored procedures, DDL, and SQL-SMO published interfaces, and works to maintain the backward compatibility of these interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d1ae1-132">não oferece suporte a gatilhos definidos nas tabelas do sistema, pois eles podem modificar a operação do sistema.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-132">does not support triggers defined on the system tables, because they might modify the operation of the system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d1ae1-133">Bancos de dados do sistema não podem residir em diretórios de compartilhamento UNC.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-133">System databases cannot reside on UNC share directories.</span></span>  
  
## <a name="viewing-system-database-data"></a><span data-ttu-id="d1ae1-134">exibindo dados de sistema do banco de dados</span><span class="sxs-lookup"><span data-stu-id="d1ae1-134">Viewing System Database Data</span></span>  
 <span data-ttu-id="d1ae1-135">Você não deve codificar instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] que fazem consulta diretamente nas tabelas do sistema, a menos que seja a única maneira de obter as informações exigidas pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-135">You should not code [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that directly query the system tables, unless that is the only way to obtain the information that is required by the application.</span></span> <span data-ttu-id="d1ae1-136">Em lugar disso, os aplicativos devem obter informações de catálogos e do sistema usando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1ae1-136">Instead, applications should obtain catalog and system information by using the following:</span></span>  
  
-   <span data-ttu-id="d1ae1-137">Exibições de catálogo do sistema</span><span class="sxs-lookup"><span data-stu-id="d1ae1-137">System catalog views</span></span>  
  
-   <span data-ttu-id="d1ae1-138">SQL-SMO</span><span class="sxs-lookup"><span data-stu-id="d1ae1-138">SQL-SMO</span></span>  
  
-   <span data-ttu-id="d1ae1-139">Interface de Instrumentação de Gerenciamento do Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="d1ae1-139">Windows Management Instrumentation (WMI) interface</span></span>  
  
-   <span data-ttu-id="d1ae1-140">Funções de catálogo, métodos, atributos, ou propriedades das API de dados usados no aplicativo, como ADO, OLE DB, ou ODBC.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-140">Catalog functions, methods, attributes, or properties of the data API used in the application, such as ADO, OLE DB, or ODBC.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="d1ae1-141">procedimentos armazenados do sistema e funções internas.</span><span class="sxs-lookup"><span data-stu-id="d1ae1-141">system stored procedures and built-in functions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d1ae1-142">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d1ae1-142">Related Tasks</span></span>  
 [<span data-ttu-id="d1ae1-143">Fazer backup e restaurar bancos de dados do sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d1ae1-143">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="d1ae1-144">Ocultar objetos do sistema no Pesquisador de objetos</span><span class="sxs-lookup"><span data-stu-id="d1ae1-144">Hide System Objects in Object Explorer</span></span>](../../ssms/object/object-explorer.md)  
  
## <a name="related-content"></a><span data-ttu-id="d1ae1-145">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="d1ae1-145">Related Content</span></span>  
 [<span data-ttu-id="d1ae1-146">Exibições de catálogo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d1ae1-146">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
 [<span data-ttu-id="d1ae1-147">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="d1ae1-147">Databases</span></span>](databases.md)  
  
  
