---
title: Visão geral da integração CLR (Common Language Runtime) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- managed code [SQL Server]
- common language runtime [SQL Server], about CLR integration
- cross-language integration
- integrating CLR [SQL Server]
- .NET Framework [SQL Server], common language runtime
- code access security [CLR integration]
- managed code [SQL Server], CLR integration
ms.assetid: 7be9e644-36a2-48fc-9206-faf59fdff4d7
author: rothja
ms.author: jroth
ms.openlocfilehash: 25345fd39fb8a77f62e4e352b75629a98cb9d7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573123"
---
# <a name="common-language-runtime-clr-integration-overview"></a><span data-ttu-id="1ad6c-102">Visão geral da integração CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="1ad6c-102">Common Language Runtime (CLR) Integration Overview</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="1ad6c-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]agora apresenta a integração do componente Common Language Runtime (CLR) do .NET Framework para [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] now features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="1ad6c-104">O CLR fornece código gerenciado com serviços como integração entre idiomas, segurança de acesso do código, gerenciamento do tempo de vida de objetos e suporte à depuração e à criação de perfis.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-104">The CLR supplies managed code with services such as cross-language integration, code access security, object lifetime management, and debugging and profiling support.</span></span> <span data-ttu-id="1ad6c-105">Para usuários e desenvolvedores de aplicativos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a integração CLR significa que agora você pode gravar procedimentos armazenados, gatilhos, tipos definidos pelo usuário, funções definidas pelo usuário (escalares e com valor de tabela) e funções de agregação definidas pelo usuário usando qualquer linguagem do .NET Framework, incluindo o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET e o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-105">For [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] users and application developers, CLR integration means that you can now write stored procedures, triggers, user-defined types, user-defined functions (scalar and table-valued), and user-defined aggregate functions using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="1ad6c-106">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] inclui o .NET Framework 4 pré-instalado.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-106">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] includes the .NET Framework version 4 pre-installed.</span></span>  
  
 <span data-ttu-id="1ad6c-107">Estes são alguns dos principais benefícios dessa integração:</span><span class="sxs-lookup"><span data-stu-id="1ad6c-107">Among the major benefits of this integration are:</span></span>  
  
-   <span data-ttu-id="1ad6c-108">**Um modelo de programação melhor.**</span><span class="sxs-lookup"><span data-stu-id="1ad6c-108">**A better programming model.**</span></span> <span data-ttu-id="1ad6c-109">Em muitos aspectos, as linguagens do .NET Framework são mais sofisticadas do que o Transact-SQL, oferecendo construções e recursos não disponíveis anteriormente aos desenvolvedores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ad6c-109">The .NET Framework languages are in many respects richer than Transact-SQL, offering constructs and capabilities previously not available to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developers.</span></span> <span data-ttu-id="1ad6c-110">Os desenvolvedores também podem aproveitar a potência da Biblioteca do .NET Framework, que fornece um abrangente conjunto de classes que podem ser usadas para resolver problemas de programação de forma rápida e eficiente.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-110">Developers may also leverage the power of the .NET Framework Library, which provides an extensive set of classes that can be used to quickly and efficiently solve programming problems.</span></span>  
  
-   <span data-ttu-id="1ad6c-111">**Proteção e segurança aprimoradas.**</span><span class="sxs-lookup"><span data-stu-id="1ad6c-111">**Improved safety and security.**</span></span> <span data-ttu-id="1ad6c-112">O código gerenciado é executado em um ambiente CLR, hospedado pelo Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-112">Managed code runs in a common language run-time environment, hosted by the Database Engine.</span></span> <span data-ttu-id="1ad6c-113">Isso é aproveitado pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para fornecer uma alternativa mais segura e protegida para os procedimentos armazenados estendidos disponíveis em versões anteriores do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ad6c-113">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] leverages this to provide a safer and more secure alternative to the extended stored procedures available in earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1ad6c-114">**Capacidade de definir tipos de dados e funções de agregação.**</span><span class="sxs-lookup"><span data-stu-id="1ad6c-114">**Ability to define data types and aggregate functions.**</span></span> <span data-ttu-id="1ad6c-115">Os tipos definidos pelo usuário e as agregações definidas pelo usuário são dois novos objetos de banco de dados gerenciados que ampliam os recursos de armazenamento e consulta do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ad6c-115">User defined types and user defined aggregates are two new managed database objects which expand the storage and querying capabilities of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1ad6c-116">**Desenvolvimento simplificado por meio de um ambiente padronizado.**</span><span class="sxs-lookup"><span data-stu-id="1ad6c-116">**Streamlined development through a standardized environment.**</span></span> <span data-ttu-id="1ad6c-117">O desenvolvimento do banco de dados será integrado em versões futuras do ambiente de desenvolvimento do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-117">Database development is integrated into future releases of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET development environment.</span></span> <span data-ttu-id="1ad6c-118">Os desenvolvedores usam as mesmas ferramentas para desenvolver e depurar scripts e objetos do banco de dados que usavam para escrever componentes e serviços de camada intermediária ou da camada de cliente do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-118">Developers use the same tools for developing and debugging database objects and scripts as they use to write middle-tier or client-tier .NET Framework components and services.</span></span>  
  
-   <span data-ttu-id="1ad6c-119">**Potencial para desempenho e escalabilidade aprimorada.**</span><span class="sxs-lookup"><span data-stu-id="1ad6c-119">**Potential for improved performance and scalability.**</span></span> <span data-ttu-id="1ad6c-120">Em muitas situações, os modelos de compilação e execução da linguagem do .NET Framework oferecem um desempenho aprimorado em relação ao Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-120">In many situations, the .NET Framework language compilation and execution models deliver improved performance over Transact-SQL.</span></span>  
  
 <span data-ttu-id="1ad6c-121">A tabela a seguir lista os tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-121">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="1ad6c-122">Visão geral da integração CLR</span><span class="sxs-lookup"><span data-stu-id="1ad6c-122">Overview of CLR Integration</span></span>](clr-integration-overview.md)  
 <span data-ttu-id="1ad6c-123">Descreve os tipos de objetos que podem ser criados por meio da integração CLR e analisa os requisitos para criar objetos de banco de dados usando a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-123">Describes the kinds of objects that can be built using CLR integration, and reviews the requirements for building database objects using CLR integration.</span></span>  
  
 [<span data-ttu-id="1ad6c-124">Novidades da integração CLR</span><span class="sxs-lookup"><span data-stu-id="1ad6c-124">What's New in CLR Integration</span></span>](clr-integration-what-s-new.md)  
 <span data-ttu-id="1ad6c-125">Descreve os novos recursos desta versão.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-125">Describes the new features in this release.</span></span>  
  
 [<span data-ttu-id="1ad6c-126">Arquitetura da integração CLR</span><span class="sxs-lookup"><span data-stu-id="1ad6c-126">Architecture of CLR Integration</span></span>](../../database-engine/dev-guide/architecture-of-clr-integration.md)  
 <span data-ttu-id="1ad6c-127">Descreve as metas de design da integração CLR.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-127">Describes the design goals of CLR integration.</span></span>  
  
 [<span data-ttu-id="1ad6c-128">Habilitando a integração CLR</span><span class="sxs-lookup"><span data-stu-id="1ad6c-128">Enabling CLR Integration</span></span>](clr-integration-enabling.md)  
 <span data-ttu-id="1ad6c-129">Descreve como habilitar a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="1ad6c-129">Describes how to enable CLR integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad6c-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1ad6c-130">See Also</span></span>  
 <span data-ttu-id="1ad6c-131">[Instalando o .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span><span class="sxs-lookup"><span data-stu-id="1ad6c-131">[Installing the .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span></span>  
 [<span data-ttu-id="1ad6c-132">Desempenho da integração CLR</span><span class="sxs-lookup"><span data-stu-id="1ad6c-132">Performance of CLR Integration</span></span>](clr-integration-architecture-performance.md)  
  
  
