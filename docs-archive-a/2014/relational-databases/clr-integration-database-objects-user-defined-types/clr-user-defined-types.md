---
title: Tipos CLR definidos pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- validation [CLR integration]
- types [CLR integration]
- UserDefined serialization format [CLR integration]
- null values [CLR integration]
- serialization
- Native serialization format [CLR integration]
- databases [CLR integration]
- building database objects [CLR integration], user-defined types
- user-defined types [CLR integration]
- common language runtime [SQL Server], user-defined types
- UDTs [CLR integration]
- database objects [CLR integration], user-defined types
- turning on CLR functionality
- customizing UDT expression return types [CLR integration]
- UDTs [CLR integration], about UDTs
- comparing UDT values
- annotations [CLR integration]
- user-defined types [CLR integration], about UDTs
- variables [CLR integration]
- invoking UDT methods
- indexes [CLR integration]
ms.assetid: 27c4889b-c543-47a8-a630-ad06804f92df
author: rothja
ms.author: jroth
ms.openlocfilehash: e4e19323eeac9e0a1148924543f71aa7de5619b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583653"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="3a225-102">Tipos definido pelo usuário CLR</span><span class="sxs-lookup"><span data-stu-id="3a225-102">CLR User-Defined Types</span></span>
  <span data-ttu-id="3a225-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dá a possibilidade para criar objetos de banco de dados programados em um assembly criado no CLR (Common Language Runtime) do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a225-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gives you the ability to create database objects that are programmed against an assembly created in the.NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="3a225-104">Os objetos do banco de dados que podem usufruir o modelo de programação avançado fornecido pelo CLR incluem gatilhos, procedimentos armazenados, funções, funções de agregação e tipos.</span><span class="sxs-lookup"><span data-stu-id="3a225-104">Database objects that can take advantage of the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a225-105">Por padrão, a possibilidade de executar código do CLR está definida como OFF no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a225-105">The ability to execute CLR code is set to OFF by default in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3a225-106">O CLR pode ser habilitado usando o procedimento armazenado do sistema **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="3a225-106">The CLR can be enabled by using the **sp_configure** system stored procedure.</span></span>  
  
 <span data-ttu-id="3a225-107">A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , você pode usar UDTs (tipos definidos pelo usuário) para estender o sistema de tipos escalares do servidor, permitindo o armazenamento de objetos CLR em um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3a225-107">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can use user-defined types (UDTs) to extend the scalar type system of the server, enabling storage of CLR objects in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="3a225-108">As UDTs podem conter vários elementos e apresentar comportamentos, o que as diferencia dos tipos de dados de alias tradicionais, que consistem em um único tipo de dados de sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a225-108">UDTs can contain multiple elements and can have behaviors, differentiating them from the traditional alias data types which consist of a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system data type.</span></span>  
  
 <span data-ttu-id="3a225-109">Como as UDTs são acessadas pelo sistema como um todo, seu uso em tipos de dados complexos pode apresentar um impacto negativo em relação ao desempenho.</span><span class="sxs-lookup"><span data-stu-id="3a225-109">Because UDTs are accessed by the system as a whole, their use for complex data types may negatively impact performance.</span></span> <span data-ttu-id="3a225-110">Dados complexos costumam ser mais bem modelados usando linhas e tabelas tradicionais.</span><span class="sxs-lookup"><span data-stu-id="3a225-110">Complex data is generally best modeled using traditional rows and tables.</span></span> <span data-ttu-id="3a225-111">As UDTs do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são bem-apropriadas ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="3a225-111">UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are well suited to the following:</span></span>  
  
-   <span data-ttu-id="3a225-112">Tipos de data, hora, moeda e numéricos estendidos</span><span class="sxs-lookup"><span data-stu-id="3a225-112">Date, time, currency, and extended numeric types</span></span>  
  
-   <span data-ttu-id="3a225-113">Aplicativos geoespaciais</span><span class="sxs-lookup"><span data-stu-id="3a225-113">Geospatial applications</span></span>  
  
-   <span data-ttu-id="3a225-114">Dados codificados ou criptografados</span><span class="sxs-lookup"><span data-stu-id="3a225-114">Encoded or encrypted data</span></span>  
  
 <span data-ttu-id="3a225-115">O processo de desenvolvimento das UDTs no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consiste nas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3a225-115">The process of developing UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="3a225-116">**Codifique e compile o assembly que define a UDT.**</span><span class="sxs-lookup"><span data-stu-id="3a225-116">**Code and build the assembly that defines the UDT.**</span></span> <span data-ttu-id="3a225-117">Os UDTs são definidos usando qualquer um dos idiomas com suporte pelo the.NET Framework Common Language Runtime (CLR) que produz código verificável.</span><span class="sxs-lookup"><span data-stu-id="3a225-117">UDTs are defined using any of the languages supported by the.NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="3a225-118">Isso inclui o Visual C# e o Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="3a225-118">This includes Visual C# and Visual Basic .NET.</span></span> <span data-ttu-id="3a225-119">Os dados são expostos como campos e propriedades de uma classe ou estrutura do .NET Framework, e os comportamentos são definidos pelos métodos da classe ou estrutura.</span><span class="sxs-lookup"><span data-stu-id="3a225-119">The data is exposed as fields and properties of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span>  
  
2.  <span data-ttu-id="3a225-120">**Registre o assembly.**</span><span class="sxs-lookup"><span data-stu-id="3a225-120">**Register the assembly.**</span></span> <span data-ttu-id="3a225-121">As UDTs podem ser implantadas por meio da interface do usuário do Visual Studio em um projeto de banco de dados ou usando a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY, que copia o assembly que contém a classe ou a estrutura para um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3a225-121">UDTs can be deployed through the Visual Studio user interface in a database project, or by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY statement, which copies the assembly containing the class or structure into a database.</span></span>  
  
3.  <span data-ttu-id="3a225-122">**Crie a UDT no SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="3a225-122">**Create the UDT in SQL Server.**</span></span> <span data-ttu-id="3a225-123">Uma vez que o assembly está carregado em um banco de dados de host, você usa a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TYPE para criar uma UDT e expor os membros da classe ou da estrutura como membros da UDT.</span><span class="sxs-lookup"><span data-stu-id="3a225-123">Once an assembly is loaded into a host database, you use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TYPE statement to create a UDT and expose the members of the class or structure as members of the UDT.</span></span> <span data-ttu-id="3a225-124">As UDTs só existem no contexto de um único banco de dados e, uma vez registradas, não têm dependências quanto a arquivos externos nos quais foram criados.</span><span class="sxs-lookup"><span data-stu-id="3a225-124">UDTs exist only in the context of a single database, and, once registered, have no dependencies on the external files from which they were created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3a225-125">Antes do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], não havia suporte para UDTs criadas em assemblies do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a225-125">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], UDTs created from .NET Framework assemblies were not supported.</span></span> <span data-ttu-id="3a225-126">No entanto, você ainda pode usar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados de alias usando **sp_addtype**.</span><span class="sxs-lookup"><span data-stu-id="3a225-126">However, you can still use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alias data types by using **sp_addtype**.</span></span> <span data-ttu-id="3a225-127">A sintaxe de CREATE TYPE pode ser usada para criar tanto tipos de dados definidos nativos definidos pelo usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quanto UDTs.</span><span class="sxs-lookup"><span data-stu-id="3a225-127">The CREATE TYPE syntax can be used for creating both native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined data types and UDTs.</span></span>  
  
4.  <span data-ttu-id="3a225-128">**Criar tabelas, variáveis ou parâmetros usando o UDT** A partir [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] do, um tipo definido pelo usuário pode ser usado como a definição de coluna de uma tabela, como uma variável em um [!INCLUDE[tsql](../../includes/tsql-md.md)] lote ou como um argumento de uma [!INCLUDE[tsql](../../includes/tsql-md.md)] função ou procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="3a225-128">**Create tables, variables, or parameters using the UDT** Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user-defined type can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a225-129">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3a225-129">In This Section</span></span>  
 [<span data-ttu-id="3a225-130">Criando um tipo definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="3a225-130">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
 <span data-ttu-id="3a225-131">Descreve como criar UDTs.</span><span class="sxs-lookup"><span data-stu-id="3a225-131">Describes how to create UDTs.</span></span>  
  
 [<span data-ttu-id="3a225-132">Registrando tipos definidos pelo usuário no SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a225-132">Registering User-Defined Types in SQL Server</span></span>](registering-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="3a225-133">Descreve como registrar e gerenciar UDTs no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a225-133">Describes how to register and manage UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="3a225-134">Trabalhando com tipos de dados definidos pelo usuário no SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a225-134">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="3a225-135">Descreve como criar consultas que usam UDTs.</span><span class="sxs-lookup"><span data-stu-id="3a225-135">Describes how to create queries using UDTs.</span></span>  
  
 [<span data-ttu-id="3a225-136">Acessando tipos definidos pelo usuário no ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3a225-136">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
 <span data-ttu-id="3a225-137">Descreve como trabalhar com UDTs que usam o provedor de dados .NET Framework do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="3a225-137">Describes how to work with UDTs using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in ADO.NET.</span></span>  
  
  
