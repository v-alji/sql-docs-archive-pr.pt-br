---
title: Restrições do modelo de programação de integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], programming model restrictions
- assemblies [CLR integration], CREATE ASSEMBLY checks
- programming model restrictions [CLR integration]
- assemblies [CLR integration], runtime checks
ms.assetid: 2446afc2-9d21-42d3-9847-7733d3074de9
author: rothja
ms.author: jroth
ms.openlocfilehash: 01a32e1460ad9c49061b39b1bdc419c7cd2f1342
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568637"
---
# <a name="clr-integration-programming-model-restrictions"></a><span data-ttu-id="de76a-102">Restrições do modelo de programação da Integração CLR</span><span class="sxs-lookup"><span data-stu-id="de76a-102">CLR Integration Programming Model Restrictions</span></span>
  <span data-ttu-id="de76a-103">Quando você está criando um procedimento armazenado gerenciado ou outro objeto de banco de dados gerenciado, há determinadas verificações de código executadas pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] realiza verificações no assembly de código gerenciado quando ele é registrado pela primeira vez no banco de dados, usando a `CREATE ASSEMBLY` instrução e também em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="de76a-103">When you are building a managed stored procedure or other managed database object, there are certain code checks performed by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs checks on the managed code assembly when it is first registered in the database, using the `CREATE ASSEMBLY` statement, and also at runtime.</span></span> <span data-ttu-id="de76a-104">O código gerenciado também é verificado em runtime porque, em um assembly, talvez haja caminhos de código que jamais possam ser alcançados em runtime.</span><span class="sxs-lookup"><span data-stu-id="de76a-104">The managed code is also checked at runtime because in an assembly there may be code paths that may never actually be reached at runtime.</span></span>  <span data-ttu-id="de76a-105">Isso proporciona flexibilidade para registrar, especialmente, assemblies de terceiros, logo um assembly não seria bloqueado quando houvesse um código 'não seguro' projetado para execução em um ambiente do cliente, mas que jamais seria executado no CLR hospedado.</span><span class="sxs-lookup"><span data-stu-id="de76a-105">This provides flexibility for registering third party assemblies, especially, so that an assembly wouldn't be blocked where there is 'unsafe' code designed to run in a client environment but would never be executed in the hosted CLR.</span></span> <span data-ttu-id="de76a-106">Os requisitos que o código gerenciado deve atender dependem se o assembly está registrado como `SAFE` , `EXTERNAL_ACCESS` ou `UNSAFE` , `SAFE` sendo o mais estrito, e está listado abaixo.</span><span class="sxs-lookup"><span data-stu-id="de76a-106">The requirements that the managed code must meet depend on whether the assembly is registered as `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`, `SAFE` being the strictest, and are listed below.</span></span>  
  
 <span data-ttu-id="de76a-107">Além das restrições colocadas nos assemblies de código gerenciado, também há permissões de segurança de código que são concedidas.</span><span class="sxs-lookup"><span data-stu-id="de76a-107">In addition to restrictions being placed on the managed code assemblies, there are also code security permissions that are granted.</span></span> <span data-ttu-id="de76a-108">O CLR (Common Language Runtime) oferece suporte a um modelo de segurança chamado segurança de acesso do código (CAS) destinado ao código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="de76a-108">The common language runtime (CLR) supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="de76a-109">Nesse modelo, são concedidas permissões a assemblies com base na identidade do código.</span><span class="sxs-lookup"><span data-stu-id="de76a-109">In this model, permissions are granted to assemblies based on the identity of the code.</span></span> <span data-ttu-id="de76a-110">Os assemblies `SAFE`, `EXTERNAL_ACCESS` e `UNSAFE` têm permissões CAS diferentes.</span><span class="sxs-lookup"><span data-stu-id="de76a-110">`SAFE`, `EXTERNAL_ACCESS`, and `UNSAFE` assemblies have different CAS permissions.</span></span> <span data-ttu-id="de76a-111">Para obter mais informações, consulte [segurança de acesso ao código de integração CLR](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="de76a-111">For more information, see [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="create-assembly-checks"></a><span data-ttu-id="de76a-112">Verificações de CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="de76a-112">CREATE ASSEMBLY Checks</span></span>  
 <span data-ttu-id="de76a-113">Quando a instrução `CREATE ASSEMBLY` é executada, as seguintes verificações são executadas em cada nível de segurança.</span><span class="sxs-lookup"><span data-stu-id="de76a-113">When the `CREATE ASSEMBLY` statement is run, the following checks are performed for each security level.</span></span>  <span data-ttu-id="de76a-114">Se houver falha em alguma verificação, `CREATE ASSEMBLY` apresentará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="de76a-114">If any check fails, `CREATE ASSEMBLY` will fail with an error message.</span></span>  
  
### <a name="global-any-security-level"></a><span data-ttu-id="de76a-115">Global (qualquer nível de segurança)</span><span class="sxs-lookup"><span data-stu-id="de76a-115">Global (any security level)</span></span>  
 <span data-ttu-id="de76a-116">Todos os assemblies referenciados devem atender a um ou mais dos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="de76a-116">All referenced assemblies must meet one or more of the following criteria:</span></span>  
  
-   <span data-ttu-id="de76a-117">O assembly já está registrado no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="de76a-117">The assembly is already registered in the database.</span></span>  
  
-   <span data-ttu-id="de76a-118">O assembly é um daqueles para os quais há suporte.</span><span class="sxs-lookup"><span data-stu-id="de76a-118">The assembly is one of the supported assemblies.</span></span> <span data-ttu-id="de76a-119">Para obter mais informações, consulte [bibliotecas de .NET Framework com suporte](supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="de76a-119">For more information, see [Supported .NET Framework Libraries](supported-net-framework-libraries.md).</span></span>  
  
-   <span data-ttu-id="de76a-120">Você está usando `CREATE ASSEMBLY FROM` o \* \<location> ,\* e todos os assemblies referenciados e suas dependências estão disponíveis no *\<location>* .</span><span class="sxs-lookup"><span data-stu-id="de76a-120">You are using `CREATE ASSEMBLY FROM`*\<location>,* and all the referenced assemblies and their dependencies are available in *\<location>*.</span></span>  
  
-   <span data-ttu-id="de76a-121">Você está usando `CREATE ASSEMBLY FROM` \* \<bytes ...> ,\* e todas as referências são especificadas por meio de bytes separados por espaço.</span><span class="sxs-lookup"><span data-stu-id="de76a-121">You are using `CREATE ASSEMBLY FROM`*\<bytes ...>,* and all the references are specified via space separated bytes.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="de76a-122">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="de76a-122">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="de76a-123">Todos os assemblies `EXTERNAL_ACCESS` devem atender aos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="de76a-123">All `EXTERNAL_ACCESS` assemblies must meet the following criteria:</span></span>  
  
-   <span data-ttu-id="de76a-124">Não são usados campos estáticos para armazenar informações.</span><span class="sxs-lookup"><span data-stu-id="de76a-124">Static fields are not used to store information.</span></span> <span data-ttu-id="de76a-125">São permitidos campos estáticos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="de76a-125">Read-only static fields are allowed.</span></span>  
  
-   <span data-ttu-id="de76a-126">O teste PEVerify passou.</span><span class="sxs-lookup"><span data-stu-id="de76a-126">PEVerify test is passed.</span></span> <span data-ttu-id="de76a-127">A ferramenta PEVerify (peverify.exe), que verifica se o código MSIL e os metadados associados atendem aos requisitos de segurança do tipo, é fornecida com o SDK do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de76a-127">The PEVerify tool (peverify.exe), which checks that the MSIL code and associated metadata meet type safety requirements, is provided with the .NET Framework SDK.</span></span>  
  
-   <span data-ttu-id="de76a-128">A sincronização, por exemplo com a classe `SynchronizationAttribute`, não é usada.</span><span class="sxs-lookup"><span data-stu-id="de76a-128">Synchronization, for example with the `SynchronizationAttribute` class, is not used.</span></span>  
  
-   <span data-ttu-id="de76a-129">Não são usados métodos Finalizer.</span><span class="sxs-lookup"><span data-stu-id="de76a-129">Finalizer methods are not used.</span></span>  
  
 <span data-ttu-id="de76a-130">Os seguintes atributos personalizados são desaprovados no assembly `EXTERNAL_ACCESS`:</span><span class="sxs-lookup"><span data-stu-id="de76a-130">The following custom attributes are disallowed in `EXTERNAL_ACCESS` assemblies:</span></span>  
  
-   <span data-ttu-id="de76a-131">System.ContextStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-131">System.ContextStaticAttribute</span></span>  
  
-   <span data-ttu-id="de76a-132">System.MTAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-132">System.MTAThreadAttribute</span></span>  
  
-   <span data-ttu-id="de76a-133">System.Runtime.CompilerServices.MethodImplAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-133">System.Runtime.CompilerServices.MethodImplAttribute</span></span>  
  
-   <span data-ttu-id="de76a-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span></span>  
  
-   <span data-ttu-id="de76a-135">System.Runtime.Remoting.Contexts.ContextAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-135">System.Runtime.Remoting.Contexts.ContextAttribute</span></span>  
  
-   <span data-ttu-id="de76a-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span></span>  
  
-   <span data-ttu-id="de76a-137">System.Runtime.InteropServices.DllImportAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-137">System.Runtime.InteropServices.DllImportAttribute</span></span>  
  
-   <span data-ttu-id="de76a-138">System.Security.Permissions.CodeAccessSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-138">System.Security.Permissions.CodeAccessSecurityAttribute</span></span>  
  
-   <span data-ttu-id="de76a-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span></span>  
  
-   <span data-ttu-id="de76a-140">System.Security.UnverifiableCodeAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-140">System.Security.UnverifiableCodeAttribute</span></span>  
  
-   <span data-ttu-id="de76a-141">System.STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-141">System.STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="de76a-142">System.ThreadStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="de76a-142">System.ThreadStaticAttribute</span></span>  
  
### <a name="safe"></a><span data-ttu-id="de76a-143">SAFE</span><span class="sxs-lookup"><span data-stu-id="de76a-143">SAFE</span></span>  
  
-   <span data-ttu-id="de76a-144">Todas as condições do assembly `EXTERNAL_ACCESS` são verificadas.</span><span class="sxs-lookup"><span data-stu-id="de76a-144">All `EXTERNAL_ACCESS` assembly conditions are checked.</span></span>  
  
## <a name="runtime-checks"></a><span data-ttu-id="de76a-145">Verificações de runtime</span><span class="sxs-lookup"><span data-stu-id="de76a-145">Runtime Checks</span></span>  
 <span data-ttu-id="de76a-146">Em runtime, o assembly do código é verificado em relação às seguintes condições.</span><span class="sxs-lookup"><span data-stu-id="de76a-146">At runtime, the code assembly is checked for the following conditions.</span></span> <span data-ttu-id="de76a-147">Se alguma dessas condições for encontrada, o código gerenciado não terá permissão de execução, e uma exceção será lançada.</span><span class="sxs-lookup"><span data-stu-id="de76a-147">If any of these conditions are found, the managed code will not be allowed to run and an exception will be thrown.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="de76a-148">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="de76a-148">UNSAFE</span></span>  
 <span data-ttu-id="de76a-149">Carregar um assembly-seja explicitamente chamando o `System.Reflection.Assembly.Load()` método de uma matriz de bytes ou implicitamente através do uso de `Reflection.Emit` namespace-não é permitido.</span><span class="sxs-lookup"><span data-stu-id="de76a-149">Loading an assembly-either explicitly by calling the `System.Reflection.Assembly.Load()` method from a byte array, or implicitly through the use of `Reflection.Emit` namespace-is not permitted.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="de76a-150">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="de76a-150">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="de76a-151">Todas as condições `UNSAFE` são verificadas.</span><span class="sxs-lookup"><span data-stu-id="de76a-151">All `UNSAFE` conditions are checked.</span></span>  
  
 <span data-ttu-id="de76a-152">São desaprovados todos os tipos e métodos anotados com os seguintes valores HPA (atributo de proteção de host) na lista de assemblies para a qual há suporte.</span><span class="sxs-lookup"><span data-stu-id="de76a-152">All types and methods annotated with the following host protection attribute (HPA) values in the supported list of assemblies are disallowed.</span></span>  
  
-   <span data-ttu-id="de76a-153">SelfAffectingProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="de76a-153">SelfAffectingProcessMgmt</span></span>  
  
-   <span data-ttu-id="de76a-154">SelfAffectingThreading</span><span class="sxs-lookup"><span data-stu-id="de76a-154">SelfAffectingThreading</span></span>  
  
-   <span data-ttu-id="de76a-155">Sincronização</span><span class="sxs-lookup"><span data-stu-id="de76a-155">Synchronization</span></span>  
  
-   <span data-ttu-id="de76a-156">SharedState</span><span class="sxs-lookup"><span data-stu-id="de76a-156">SharedState</span></span>  
  
-   <span data-ttu-id="de76a-157">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="de76a-157">ExternalProcessMgmt</span></span>  
  
-   <span data-ttu-id="de76a-158">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="de76a-158">ExternalThreading</span></span>  
  
-   <span data-ttu-id="de76a-159">SecurityInfrastructure</span><span class="sxs-lookup"><span data-stu-id="de76a-159">SecurityInfrastructure</span></span>  
  
-   <span data-ttu-id="de76a-160">MayLeakOnAbort</span><span class="sxs-lookup"><span data-stu-id="de76a-160">MayLeakOnAbort</span></span>  
  
-   <span data-ttu-id="de76a-161">UI</span><span class="sxs-lookup"><span data-stu-id="de76a-161">UI</span></span>  
  
 <span data-ttu-id="de76a-162">Para obter mais informações sobre HPAs e uma lista de tipos não permitidos e membros nos assemblies com suporte, consulte [atributos de proteção do host e programação de integração do CLR](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span><span class="sxs-lookup"><span data-stu-id="de76a-162">For more information about HPAs and a list of disallowed types and members in the supported assemblies, see [Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span></span>  
  
### <a name="safe"></a><span data-ttu-id="de76a-163">SAFE</span><span class="sxs-lookup"><span data-stu-id="de76a-163">SAFE</span></span>  
 <span data-ttu-id="de76a-164">Todas as condições `EXTERNAL_ACCESS` são verificadas.</span><span class="sxs-lookup"><span data-stu-id="de76a-164">All `EXTERNAL_ACCESS` conditions are checked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de76a-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de76a-165">See Also</span></span>  
 <span data-ttu-id="de76a-166">[Bibliotecas de .NET Framework com suporte](supported-net-framework-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="de76a-166">[Supported .NET Framework Libraries](supported-net-framework-libraries.md) </span></span>  
 <span data-ttu-id="de76a-167">[Segurança de acesso ao código de integração CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="de76a-167">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="de76a-168">[Atributos de proteção do host e programação de integração CLR](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="de76a-168">[Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 [<span data-ttu-id="de76a-169">Criando um assembly</span><span class="sxs-lookup"><span data-stu-id="de76a-169">Creating an Assembly</span></span>](../assemblies/creating-an-assembly.md)  
  
  
