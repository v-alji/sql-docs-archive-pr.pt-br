---
title: Segurança de integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- authorization [CLR integration]
- common language runtime [SQL Server], security
- database objects [CLR integration], security
ms.assetid: 05d7a471-c5d5-4730-b903-e4edc8157bb4
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d99d32a061d8fe78a8ac3642a503cceb45f3809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572587"
---
# <a name="clr-integration-security"></a><span data-ttu-id="62c13-102">Segurança da integração CLR</span><span class="sxs-lookup"><span data-stu-id="62c13-102">CLR Integration Security</span></span>
  <span data-ttu-id="62c13-103">O modelo de segurança do [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR) gerencia e protege o acesso entre diferentes tipos de objetos CLR e não CLR em execução na [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] instrução ou outro objeto CLR em execução no servidor.</span><span class="sxs-lookup"><span data-stu-id="62c13-103">The security model of the [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] statement or another CLR object running in the server.</span></span> <span data-ttu-id="62c13-104">As chamadas entre objetos conhecidas como links.</span><span class="sxs-lookup"><span data-stu-id="62c13-104">The calls between objects are referred to as links.</span></span> <span data-ttu-id="62c13-105">Os tipos de verificações de segurança realizados nesses objetos dependem dos tipos de links envolvidos.</span><span class="sxs-lookup"><span data-stu-id="62c13-105">The types of security checks performed on these objects depend on the types of links involved.</span></span>  
  
 <span data-ttu-id="62c13-106">O modelo de segurança de integração do CLR tem as seguintes metas:</span><span class="sxs-lookup"><span data-stu-id="62c13-106">The CLR integration security model has the following goals:</span></span>  
  
-   <span data-ttu-id="62c13-107">Por padrão, a execução de código de usuário gerenciado no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62c13-107">By default, running managed user code on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="62c13-108">Realizar operações que podem comprometem a eficiência do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deve ser protegido por meio de permissões de alto nível apropriadas.</span><span class="sxs-lookup"><span data-stu-id="62c13-108">Performing operations that potentially compromise the robustness of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should be protected by appropriate high-level permissions.</span></span>  
  
-   <span data-ttu-id="62c13-109">O código de usuário gerenciado não deve ter acesso não autorizado a dados de usuário ou outro código de usuário no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="62c13-109">Managed user code should not gain unauthorized access to user data or other user code in the database.</span></span> <span data-ttu-id="62c13-110">O código definido pelo usuário deve ser executado no contexto de segurança da sessão do usuário que o invocou e com os privilégios corretos para o contexto de segurança.</span><span class="sxs-lookup"><span data-stu-id="62c13-110">User-defined code should run under the security context of the user-session that invoked it, and with the correct privileges for that security context.</span></span>  
  
-   <span data-ttu-id="62c13-111">Deve haver controles para impedir que o código do usuário acesse qualquer recurso fora do servidor, usando-o estritamente para acesso a dados locais e computação.</span><span class="sxs-lookup"><span data-stu-id="62c13-111">There should be controls for restricting user code from accessing any resources outside the server, using it strictly for local data access and computation.</span></span>  
  
-   <span data-ttu-id="62c13-112">O código definido pelo usuário não deve obter acesso não autorizado a recursos do sistema em virtude da execução no processo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62c13-112">User-defined code should not be able to gain unauthorized access to system resources by virtue of running in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="62c13-113">com o modelo de segurança baseado em acesso ao código do CLR.</span><span class="sxs-lookup"><span data-stu-id="62c13-113">with the code access-based security model of the CLR.</span></span> <span data-ttu-id="62c13-114">Algumas das vantagens dessa abordagem combinada em relação à segurança são abordadas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="62c13-114">Some of the advantages of this combined approach to security are discussed in this section.</span></span>  
  
 <span data-ttu-id="62c13-115">A tabela a seguir lista os tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="62c13-115">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="62c13-116">Segurança de acesso a código da integração CLR</span><span class="sxs-lookup"><span data-stu-id="62c13-116">CLR Integration Code Access Security</span></span>](clr-integration-code-access-security.md)  
 <span data-ttu-id="62c13-117">Discute o modelo CAS (segurança de acesso do código) para código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="62c13-117">Discusses the code access security (CAS) model for managed code.</span></span>  
  
 [<span data-ttu-id="62c13-118">Atributos de proteção de host e programação da Integração CLR</span><span class="sxs-lookup"><span data-stu-id="62c13-118">Host Protection Attributes and CLR Integration Programming</span></span>](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md)  
 <span data-ttu-id="62c13-119">Fornece informações sobre valores HPA (atributo de proteção do host) que são desaprovados nos assemblies SAFE e EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="62c13-119">Provides information about the host protection attribute (HPA) values that are disallowed in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
 [<span data-ttu-id="62c13-120">Links em segurança da integração CLR</span><span class="sxs-lookup"><span data-stu-id="62c13-120">Links in CLR Integration Security</span></span>](../../../database-engine/dev-guide/links-in-clr-integration-security.md)  
 <span data-ttu-id="62c13-121">Descreve como partes do código do usuário podem se chamar uma à outra no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62c13-121">Describes how pieces of user-code can call each other in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="62c13-122">Representação e segurança de integração CLR</span><span class="sxs-lookup"><span data-stu-id="62c13-122">Impersonation and CLR Integration Security</span></span>](../../../database-engine/dev-guide/impersonation-and-clr-integration-security.md)  
 <span data-ttu-id="62c13-123">Aborda como o código gerenciado acessa recursos externos que usam representação.</span><span class="sxs-lookup"><span data-stu-id="62c13-123">Discusses how managed code accesses external resources using impersonation.</span></span>  
  
 [<span data-ttu-id="62c13-124">Permitindo chamadores parcialmente confiáveis</span><span class="sxs-lookup"><span data-stu-id="62c13-124">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
 <span data-ttu-id="62c13-125">Aborda problemas que surgem quando um método gerenciado invoca um método em uma classe contida em outro assembly.</span><span class="sxs-lookup"><span data-stu-id="62c13-125">Discusses issues that arise when a managed method invokes a method in a class contained in another assembly.</span></span>  
  
 [<span data-ttu-id="62c13-126">Domínios do aplicativo e segurança da integração CLR</span><span class="sxs-lookup"><span data-stu-id="62c13-126">Application Domains and CLR Integration Security</span></span>](../../../database-engine/dev-guide/application-domains-and-clr-integration-security.md)  
 <span data-ttu-id="62c13-127">Descreve como os assemblies são carregados em domínios de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="62c13-127">Describes how assemblies are loaded into application domains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c13-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="62c13-128">See Also</span></span>  
 [<span data-ttu-id="62c13-129">Gerenciando assemblies de integração CLR</span><span class="sxs-lookup"><span data-stu-id="62c13-129">Managing CLR Integration Assemblies</span></span>](../assemblies/managing-clr-integration-assemblies.md)  
  
  
