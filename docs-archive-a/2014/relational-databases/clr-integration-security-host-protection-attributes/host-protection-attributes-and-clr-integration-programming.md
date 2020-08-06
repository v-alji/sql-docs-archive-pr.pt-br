---
title: Atributos de proteção do host e programação de integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- HostProtectionAttribute [CLR integration]
- common language runtime [SQL Server], host protection attributes
- disallowed types and members [CLR integration]
- common language runtime [SQL Server], disallowed types and members
- HPAs [CLR integration]
ms.assetid: 268078df-63ca-4c03-a8e7-7108bcea9697
author: rothja
ms.author: jroth
ms.openlocfilehash: 16ca1e4734e66b0eca85523764739e8f8b32634a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682298"
---
# <a name="host-protection-attributes-and-clr-integration-programming"></a><span data-ttu-id="a8565-102">Atributos de proteção de host e programação da Integração CLR</span><span class="sxs-lookup"><span data-stu-id="a8565-102">Host Protection Attributes and CLR Integration Programming</span></span>
  <span data-ttu-id="a8565-103">O CLR (Common Language Runtime) fornece um mecanismo para anotar APIs (interfaces de programação de aplicativo ) gerenciadas que fazem parte do .NET Framework com determinados atributos que podem ser de interesse de um host do CLR como, por exemplo, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], desde o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8565-103">The common language runtime (CLR) provides a mechanism to annotate managed application programming interfaces (APIs) that are part of the .NET Framework with certain attributes that may be of interest to a host of the CLR, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="a8565-104">Entre os exemplos desses HPAs (atributos de proteção de host) estão:</span><span class="sxs-lookup"><span data-stu-id="a8565-104">Examples of such host protection attributes (HPAs) include:</span></span>  
  
-   <span data-ttu-id="a8565-105">`SharedState`, que indica se a API expõe a capacidade de criar ou gerenciar estado compartilhado (por exemplo, campos de classe estáticos).</span><span class="sxs-lookup"><span data-stu-id="a8565-105">`SharedState`, which indicates whether the API exposes the ability to create or manage shared state (for example, static class fields).</span></span>  
  
-   <span data-ttu-id="a8565-106">`Synchronization`, que indica se a API expõe a capacidade para executar sincronização entre threads.</span><span class="sxs-lookup"><span data-stu-id="a8565-106">`Synchronization`, which indicates whether the API exposes the ability to perform synchronization between threads.</span></span>  
  
-   <span data-ttu-id="a8565-107">`ExternalProcessMgmt`, que indica se a API expõe um modo de controlar o processo de host.</span><span class="sxs-lookup"><span data-stu-id="a8565-107">`ExternalProcessMgmt`, which indicates whether the API exposes a way to control the host process.</span></span>  
  
 <span data-ttu-id="a8565-108">Dados esses atributos, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especifica uma lista de HPAs desaprovadas no ambiente hospedado por meio da CAS (segurança de acesso do código).</span><span class="sxs-lookup"><span data-stu-id="a8565-108">Given these attributes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specifies a list of HPAs that are disallowed in the hosted environment through code access security (CAS).</span></span> <span data-ttu-id="a8565-109">Os requisitos de CAs são especificados por um dos três conjuntos de permissões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: `SAFE`, `EXTERNAL_ACCESS` ou `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="a8565-109">The CAS requirements are specified by one of three [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission sets: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="a8565-110">Um desses três níveis de segurança é especificado quando o assembly é registrado no servidor, usando a instrução `CREATE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="a8565-110">One of these three security levels is specified when the assembly is registered on the server, using the `CREATE ASSEMBLY` statement.</span></span> <span data-ttu-id="a8565-111">Código em execução nos conjuntos de permissões `SAFE` ou `EXTERNAL_ACCESS` deve evitar determinados tipos ou membros que tenham o atributo `System.Security.Permissions.HostProtectionAttribute` aplicado.</span><span class="sxs-lookup"><span data-stu-id="a8565-111">Code executing within the `SAFE` or `EXTERNAL_ACCESS` permission sets must avoid certain types or members that have the `System.Security.Permissions.HostProtectionAttribute` attribute applied.</span></span> <span data-ttu-id="a8565-112">Para obter mais informações, consulte [criando um assembly](../clr-integration/assemblies/creating-an-assembly.md) e [restrições de modelo de programação de integração CLR](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="a8565-112">For more information, see [Creating an Assembly](../clr-integration/assemblies/creating-an-assembly.md) and [CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span></span>  
  
 <span data-ttu-id="a8565-113">`HostProtectionAttribute` não é uma permissão de segurança tanto quanto uma forma de aumentar a confiabilidade; ela identifica construções de código específicas, tipos ou métodos, que o host pode desautorizar.</span><span class="sxs-lookup"><span data-stu-id="a8565-113">The `HostProtectionAttribute` is not a security permission as much as a way to improve reliability, in that it identifies specific code constructs, either types or methods, that the host may disallow.</span></span> <span data-ttu-id="a8565-114">O uso do `HostProtectionAttribute` impõe um modelo de programação que ajuda a proteger a estabilidade do host.</span><span class="sxs-lookup"><span data-stu-id="a8565-114">The use of the `HostProtectionAttribute` enforces a programming model that helps protect the stability of the host.</span></span>  
  
## <a name="host-protection-attributes"></a><span data-ttu-id="a8565-115">Atributos de proteção de host</span><span class="sxs-lookup"><span data-stu-id="a8565-115">Host Protection Attributes</span></span>  
 <span data-ttu-id="a8565-116">HPAs identificam tipos ou membros que não se ajustam ao modelo de programação de host e representam os seguintes níveis crescentes de ameaça à confiabilidade:</span><span class="sxs-lookup"><span data-stu-id="a8565-116">HPAs identify types or members that do not fit the host programming model and represent the following increasing levels of reliability threat:</span></span>  
  
-   <span data-ttu-id="a8565-117">Do contrário, benignos.</span><span class="sxs-lookup"><span data-stu-id="a8565-117">Are otherwise benign.</span></span>  
  
-   <span data-ttu-id="a8565-118">Poderia levar à desestabilização do código de usuário gerenciado por servidor.</span><span class="sxs-lookup"><span data-stu-id="a8565-118">Could lead to destabilization of server-managed user code.</span></span>  
  
-   <span data-ttu-id="a8565-119">Poderia levar à desestabilização do próprio processo do servidor.</span><span class="sxs-lookup"><span data-stu-id="a8565-119">Could lead to destabilization of the server process itself.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="a8565-120">Não permite o uso de um tipo ou membro que tenha um `HostProtectionAttribute` que especifique uma `System.Security.Permissions.HostProtectionResource` enumeração com um valor de,,,,,, `ExternalProcessMgmt` `ExternalThreading` `MayLeakOnAbort` `SecurityInfrastructure` `SelfAffectingProcessMgmnt` `SelfAffectingThreading` `SharedState` , `Synchronization` ou `UI` .</span><span class="sxs-lookup"><span data-stu-id="a8565-120">disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, `SharedState`, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="a8565-121">Isso impede que os assemblies chamem membros que permitam compartilhar o estado, realizar a sincronização, causar um vazamento de recurso na terminação ou afetar a integridade do processo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8565-121">This prevents the assemblies from calling members that enable sharing state, perform synchronization, might cause a resource leak on termination, or affect the integrity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="disallowed-types-and-members"></a><span data-ttu-id="a8565-122">Tipos e membros desaprovados</span><span class="sxs-lookup"><span data-stu-id="a8565-122">Disallowed Types and Members</span></span>  
 <span data-ttu-id="a8565-123">Os seguintes tópicos identificam tipos e membros cujos valores `HostProtectionResource` são desaprovados por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8565-123">The following topics identify types and members whose `HostProtectionResource` values are disallowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8565-124">As listas deste tópico foram geradas dos assembly com suporte.</span><span class="sxs-lookup"><span data-stu-id="a8565-124">The lists in these topics were generated from the supported assemblies.</span></span>  <span data-ttu-id="a8565-125">Para obter mais informações, consulte [bibliotecas de .NET Framework com suporte](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="a8565-125">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8565-126">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a8565-126">In This Section</span></span>  
 [<span data-ttu-id="a8565-127">Tipos desaprovados e membros em Microsoft.VisualBasic.dll</span><span class="sxs-lookup"><span data-stu-id="a8565-127">Disallowed Types and Members in Microsoft.VisualBasic.dll</span></span>](disallowed-types-and-members-in-microsoft-visualbasic-dll.md)  
 <span data-ttu-id="a8565-128">Lista os tipos e os membros de Microsoft.VisualBasic.dll cujos valores HPA não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a8565-128">Lists the types and members in Microsoft.VisualBasic.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="a8565-129">Membros e tipos não permitidos em mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="a8565-129">Disallowed Types and Members in mscorlib.dll</span></span>](disallowed-types-and-members-in-mscorlib-dll.md)  
 <span data-ttu-id="a8565-130">Lista os tipos e os membros de mscorlib.dll cujos valores HPA são desaprovados.</span><span class="sxs-lookup"><span data-stu-id="a8565-130">Lists the types and members in mscorlib.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="a8565-131">Disallowed Types and Members In System.dll</span><span class="sxs-lookup"><span data-stu-id="a8565-131">Disallowed Types and Members in System.dll</span></span>](disallowed-types-and-members-in-system-dll.md)  
 <span data-ttu-id="a8565-132">Lista os tipos e os membros de System.dll cujos valores HPA são desaprovados.</span><span class="sxs-lookup"><span data-stu-id="a8565-132">Lists the types and members in System.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="a8565-133">Tipos e membros não permitidos em System.Data.dll</span><span class="sxs-lookup"><span data-stu-id="a8565-133">Disallowed Types and Members in System.Data.dll</span></span>](disallowed-types-and-members-in-system-data-dll.md)  
 <span data-ttu-id="a8565-134">Lista os tipos e os membros de System.Data.dll cujos valores HPA são desaprovados.</span><span class="sxs-lookup"><span data-stu-id="a8565-134">Lists the types and members in System.Data.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="a8565-135">Tipos e membros desaprovados no System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a8565-135">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
 <span data-ttu-id="a8565-136">Lista os tipos e os membros de System.Core.dll cujos valores HPA são desaprovados.</span><span class="sxs-lookup"><span data-stu-id="a8565-136">Lists the types and members in System.Core.dll whose HPA values are disallowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8565-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a8565-137">See Also</span></span>  
 <span data-ttu-id="a8565-138">[Segurança de acesso ao código de integração CLR](../clr-integration/security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="a8565-138">[CLR Integration Code Access Security](../clr-integration/security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="a8565-139">[Restrições do modelo de programação de integração CLR](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span><span class="sxs-lookup"><span data-stu-id="a8565-139">[CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span></span>  
 [<span data-ttu-id="a8565-140">Criando um assembly</span><span class="sxs-lookup"><span data-stu-id="a8565-140">Creating an Assembly</span></span>](../clr-integration/assemblies/creating-an-assembly.md)  
  
  
