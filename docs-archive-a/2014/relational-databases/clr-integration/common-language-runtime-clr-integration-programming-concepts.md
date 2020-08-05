---
title: Conceitos de programação de integração do CLR (Common Language Runtime) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- CLR [SQL Server] See common language runtime [SQL Server]
- Database Engine [SQL Server], .NET Framework
- .NET Framework [SQL Server], Database Engine programming
- common language runtime [SQL Server]
- .NET Framework [SQL Server]
ms.assetid: 951bf851-3e6e-4361-ae6a-2bcd5b837ebd
author: rothja
ms.author: jroth
ms.openlocfilehash: 38323b0145132ad60d59c001d5147a7d19942462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572590"
---
# <a name="common-language-runtime-clr-integration-programming-concepts"></a><span data-ttu-id="efc4b-102">Conceitos de programação da Integração CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="efc4b-102">Common Language Runtime (CLR) Integration Programming Concepts</span></span>
  <span data-ttu-id="efc4b-103">A partir do [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] apresenta a integração do componente CLR do .NET Framework para o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="efc4b-103">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="efc4b-104">Isso significa que você pode agora gravar procedimentos armazenados, gatilhos, tipos definidos pelo usuário, funções definidas pelo usuário, agregações definidas pelo usuário e funções de streaming com valor de tabela, usando qualquer linguagem do .NET Framework, incluindo o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET e o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="efc4b-104">This means that you can now write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="efc4b-105">O namespace Microsoft.SqlServer.Server inclui a funcionalidade principal para programação de CLR no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efc4b-105">The Microsoft.SqlServer.Server namespace includes core functionality for CLR programming in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="efc4b-106">Porém, o namespace Microsoft.SqlServer.Server é documentado no .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="efc4b-106">However, the Microsoft.SqlServer.Server namespace is documented in the .NET Framework SDK.</span></span> <span data-ttu-id="efc4b-107">Esta documentação não é incluída em Manuais Online do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efc4b-107">This documentation is not included in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="efc4b-108">Por padrão, o .NET Framework é instalado com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], mas não o .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="efc4b-108">By default, the .NET Framework is installed with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but the .NET Framework SDK is not.</span></span> <span data-ttu-id="efc4b-109">Sem o SDK instalado no computador e incluído na coleção de Manuais Online, os links para o conteúdo do SDK desta seção não funciona.</span><span class="sxs-lookup"><span data-stu-id="efc4b-109">Without the SDK installed on your computer and included in the Books Online collection, links to SDK content in this section do not work.</span></span> <span data-ttu-id="efc4b-110">Instale o .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="efc4b-110">Install the .NET Framework SDK.</span></span> <span data-ttu-id="efc4b-111">Depois de instalado, adicione o SDK à coleção e ao Sumário dos manuais online seguindo as instruções em [instalando o SDK do .NET Framework](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="efc4b-111">Once installed, add the SDK to the Books Online collection and table of contents by following the instructions in [Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span></span>  
  
 <span data-ttu-id="efc4b-112">A tabela a seguir lista os tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="efc4b-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="efc4b-113">Visão geral da integração do CLR&#41; &#40;Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="efc4b-113">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](common-language-runtime-integration-overview.md)  
 <span data-ttu-id="efc4b-114">Fornece uma visão geral breve do CLR e descreve como e por que essa tecnologia foi usada no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efc4b-114">Provides a brief overview of the CLR, and describes how and why this technology has been used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="efc4b-115">Descreve os benefícios de usar o CLR para criar objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="efc4b-115">Describes the benefits of using the CLR to create database objects.</span></span>  
  
 [<span data-ttu-id="efc4b-116">Assemblies &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="efc4b-116">Assemblies &#40;Database Engine&#41;</span></span>](assemblies-database-engine.md)  
 <span data-ttu-id="efc4b-117">Descreve como os assemblies são usados no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para implantar funções, procedimentos armazenados, gatilhos e agregações e tipos definidos pelo usuário, escritos em uma das linguagens de código gerenciado hospedadas pelo CLR (Common Language Runtime) do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework, e não escritos no [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efc4b-117">Describes how assemblies are used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework common language runtime (CLR), and not written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 [<span data-ttu-id="efc4b-118">Criando objetos de banco de dados com o Common Language Runtime &#40;integração de&#41; CLR</span><span class="sxs-lookup"><span data-stu-id="efc4b-118">Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration</span></span>](database-objects/building-database-objects-with-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="efc4b-119">Descreve os tipos de objetos que podem ser compilados usando o CLR e examina os requisitos para compilar objetos de banco de dados de CLR.</span><span class="sxs-lookup"><span data-stu-id="efc4b-119">Describes the kinds of objects that can be built using the CLR, and reviews the requirements for building CLR database objects.</span></span>  
  
 [<span data-ttu-id="efc4b-120">Acesso aos dados dos objetos de banco de dados CLR</span><span class="sxs-lookup"><span data-stu-id="efc4b-120">Data Access from CLR Database Objects</span></span>](data-access/data-access-from-clr-database-objects.md)  
 <span data-ttu-id="efc4b-121">Descreve como uma rotina de CLR pode acessar dados armazenados em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efc4b-121">Describes how a CLR routine can access data stored in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="efc4b-122">Segurança da integração CLR</span><span class="sxs-lookup"><span data-stu-id="efc4b-122">CLR Integration Security</span></span>](security/clr-integration-security.md)  
 <span data-ttu-id="efc4b-123">Descreve o modelo de segurança da integração CLR.</span><span class="sxs-lookup"><span data-stu-id="efc4b-123">Describes the CLR integration security model.</span></span>  
  
 [<span data-ttu-id="efc4b-124">Depurando objetos de banco de dados CLR</span><span class="sxs-lookup"><span data-stu-id="efc4b-124">Debugging CLR Database Objects</span></span>](debugging-clr-database-objects.md)  
 <span data-ttu-id="efc4b-125">Descreve limitações e requisitos para depurar objetos de banco de dados de CLR.</span><span class="sxs-lookup"><span data-stu-id="efc4b-125">Describes limitations of and requirements for debugging CLR database objects.</span></span>  
  
 [<span data-ttu-id="efc4b-126">Implantando objetos de banco de dados CLR</span><span class="sxs-lookup"><span data-stu-id="efc4b-126">Deploying CLR Database Objects</span></span>](deploying-clr-database-objects.md)  
 <span data-ttu-id="efc4b-127">Descreve a implantação de assemblies para servidores de produção.</span><span class="sxs-lookup"><span data-stu-id="efc4b-127">Describes deploying assemblies to production servers.</span></span>  
  
 [<span data-ttu-id="efc4b-128">Gerenciando assemblies de integração CLR</span><span class="sxs-lookup"><span data-stu-id="efc4b-128">Managing CLR Integration Assemblies</span></span>](assemblies/managing-clr-integration-assemblies.md)  
 <span data-ttu-id="efc4b-129">Descreve como criar e descartar assemblies de integração CLR.</span><span class="sxs-lookup"><span data-stu-id="efc4b-129">Describes how to create and drop CLR integration assemblies.</span></span>  
  
 [<span data-ttu-id="efc4b-130">Monitorando e diagnosticando objetos de banco de dados gerenciado</span><span class="sxs-lookup"><span data-stu-id="efc4b-130">Monitoring and Troubleshooting Managed Database Objects</span></span>](monitoring-and-troubleshooting-managed-database-objects.md)  
 <span data-ttu-id="efc4b-131">Fornece informações sobre as ferramentas que podem ser usadas para monitorar e solucionar problemas em objetos de bancos de dados gerenciados e assemblies que são executados no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efc4b-131">Provides information about the tools that can be used to monitor and troubleshoot managed database objects and assemblies running in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="efc4b-132">Cenários de uso e exemplos para a integração do CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="efc4b-132">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="efc4b-133">Descreve casos de uso e exemplos de códigos que usam objetos CLR.</span><span class="sxs-lookup"><span data-stu-id="efc4b-133">Describes usage scenarios and code samples using CLR objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc4b-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="efc4b-134">See Also</span></span>  
 <span data-ttu-id="efc4b-135">[Assemblies &#40;Mecanismo de Banco de Dados&#41;](assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="efc4b-135">[Assemblies &#40;Database Engine&#41;](assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="efc4b-136">[Instalando o SDK do .NET Framework](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="efc4b-136">[Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span></span>  
  
  
