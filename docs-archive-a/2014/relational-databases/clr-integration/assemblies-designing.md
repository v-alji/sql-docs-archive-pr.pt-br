---
title: Projetando assemblies | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- designing assemblies [SQL Server]
- assemblies [CLR integration], designing
ms.assetid: 9c07f706-6508-41aa-a4d7-56ce354f9061
author: rothja
ms.author: jroth
ms.openlocfilehash: 785ab80a529140a52ec18ef96ccaaeafd03698cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682295"
---
# <a name="designing-assemblies"></a><span data-ttu-id="ba8bb-102">Criação de Assemblies</span><span class="sxs-lookup"><span data-stu-id="ba8bb-102">Designing Assemblies</span></span>
  <span data-ttu-id="ba8bb-103">Este tópico descreve os seguintes fatores que você deve considerar ao projetar assemblies:</span><span class="sxs-lookup"><span data-stu-id="ba8bb-103">This topic describes the following factors you should consider when you design assemblies:</span></span>  
  
-   <span data-ttu-id="ba8bb-104">Assemblies de empacotamento</span><span class="sxs-lookup"><span data-stu-id="ba8bb-104">Packaging assemblies</span></span>  
  
-   <span data-ttu-id="ba8bb-105">Gerenciando a segurança do assembly</span><span class="sxs-lookup"><span data-stu-id="ba8bb-105">Managing assembly security</span></span>  
  
-   <span data-ttu-id="ba8bb-106">Restrições em assemblies</span><span class="sxs-lookup"><span data-stu-id="ba8bb-106">Restrictions on assemblies</span></span>  
  
## <a name="packaging-assemblies"></a><span data-ttu-id="ba8bb-107">Empacotando assemblies</span><span class="sxs-lookup"><span data-stu-id="ba8bb-107">Packaging Assemblies</span></span>  
 <span data-ttu-id="ba8bb-108">Um assembly pode conter funcionalidade para mais de uma rotina do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou tipo em suas classes e métodos.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-108">An assembly can contain functionality for more than one [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] routine or type in its classes and methods.</span></span> <span data-ttu-id="ba8bb-109">A maior parte do tempo, faz sentido empacotar a funcionalidade de rotinas que executam funções relacionadas dentro do mesmo assembly, especialmente se essas rotinas compartilharem classes cujos métodos chamam um ao outro.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-109">Most of the time, it makes sense to package the functionality of routines that perform related functions within the same assembly, especially if these routines share classes whose methods call one another.</span></span> <span data-ttu-id="ba8bb-110">Por exemplo, classes que executam tarefas de gerenciamento de entrada de dados para gatilhos CLR (Common Language Runtime) e procedimentos armazenados CLR podem ser empacotados no mesmo assembly.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-110">For example, classes that perform data entry management tasks for common language runtime (CLR) triggers and CLR stored procedures can be packaged in the same assembly.</span></span> <span data-ttu-id="ba8bb-111">Isso porque os métodos para essas classes têm maior probabilidade de chamar um ao outro do que aqueles de tarefas menos relacionadas.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-111">This is because the methods for these classes are more likely to call each other than those of less related tasks.</span></span>  
  
 <span data-ttu-id="ba8bb-112">Quando você estiver empacotando código em um assembly, você deverá considerar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ba8bb-112">When you are packaging code into assembly, you should consider the following:</span></span>  
  
-   <span data-ttu-id="ba8bb-113">Tipos de dados CLR definidos pelo usuário e índices que dependem de funções CLR definidas pelo usuário podem fazer com que dados persistentes fiquem no banco de dados que dependem do assembly.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-113">CLR user-defined types and indexes that depend on CLR user-defined functions can cause persisted data to be in the database that depends on the assembly.</span></span> <span data-ttu-id="ba8bb-114">Modificar o código de um assembly é frequentemente mais complexo quando há dados persistentes que dependem do assembly no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-114">Modifying the code of an assembly is frequently more complex when there is persisted data that depends on the assembly in the database.</span></span> <span data-ttu-id="ba8bb-115">Portanto, geralmente é melhor separar o código onde haja dependências de dados persistentes (como tipos definidos pelo usuário e índices com funções definidas pelo usuário) do código que não tenha tal dependência de dados persistentes.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-115">Therefore, it is generally better to separate code on which persisted data dependencies rely (such as user-defined types and indexes using user-defined functions) from code that does not have such persisted data dependencies.</span></span> <span data-ttu-id="ba8bb-116">Para obter mais informações, consulte [implementando assemblies](assemblies-implementing.md) e [ALTER assembly &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba8bb-116">For more information, see [Implementing Assemblies](assemblies-implementing.md) and [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
-   <span data-ttu-id="ba8bb-117">Se uma parte do código gerenciado requerer permissão mais alta, será melhor separar aquele código em um assembly separado do código que não requer tal permissão.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-117">If a piece of managed code requires higher permission, it is better to separate that code into a separate assembly from code that does not require higher permission.</span></span>  
  
## <a name="managing-assembly-security"></a><span data-ttu-id="ba8bb-118">Gerenciando segurança de assembly</span><span class="sxs-lookup"><span data-stu-id="ba8bb-118">Managing Assembly Security</span></span>  
 <span data-ttu-id="ba8bb-119">Você pode controlar quanto um assembly pode acessar recursos protegidos por Código de .NET Access Security quando executar código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-119">You can control how much an assembly can access resources protected by .NET Code Access Security when it runs managed code.</span></span> <span data-ttu-id="ba8bb-120">Você faz isto especificando um de três conjuntos de permissão quando você cria ou modifica um assembly: SAFE, EXTERNAL_ACCESS ou UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-120">You do this by specifying one of three permission sets when you create or modify an assembly: SAFE, EXTERNAL_ACCESS, or UNSAFE.</span></span>  
  
### <a name="safe"></a><span data-ttu-id="ba8bb-121">SAFE</span><span class="sxs-lookup"><span data-stu-id="ba8bb-121">SAFE</span></span>  
 <span data-ttu-id="ba8bb-122">SAFE é o conjunto de permissões padrão e é o mais restritivo.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-122">SAFE is the default permission set and it is the most restrictive.</span></span> <span data-ttu-id="ba8bb-123">Código executado por um assembly com permissões SAFE não pode acessar recursos do sistema externo, como arquivos, rede, variáveis de ambiente ou Registro.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-123">Code run by an assembly with SAFE permissions cannot access external system resources such as files, the network, environment variables, or the registry.</span></span> <span data-ttu-id="ba8bb-124">O código SAFE pode acessar dados dos bancos de dados locais do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou pode executar computações e lógica empresarial que não envolvam acesso de recursos fora dos bancos de dados locais.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-124">SAFE code can access data from the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases or perform computations and business logic that do not involve accessing resources outside the local databases.</span></span>  
  
 <span data-ttu-id="ba8bb-125">A maioria dos assemblies executa tarefas de computação e gerenciamento de dados sem ter de acessar recursos fora do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba8bb-125">Most assemblies perform computation and data management tasks without having to access resources outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ba8bb-126">Portanto, nós recomendamos SAFE como conjunto de permissões de assembly.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-126">Therefore, we recommend SAFE as the assembly permission set.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="ba8bb-127">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="ba8bb-127">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="ba8bb-128">EXTERNAL_ACCESS permite que assemblies acessem certos recursos do sistema externo como arquivos, redes, serviços da Web, variáveis ambientais e Registro.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-128">EXTERNAL_ACCESS allows for assemblies to access certain external system resources such as files, networks, Web services, environmental variables, and the registry.</span></span> <span data-ttu-id="ba8bb-129">Somente logons do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com permissões EXTERNAL ACCESS podem criar assemblies EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-129">Only [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins with EXTERNAL ACCESS permissions can create EXTERNAL_ACCESS assemblies.</span></span>  
  
 <span data-ttu-id="ba8bb-130">Assemblies SAFE e EXTERNAL_ACCESS só podem conter código do tipo seguro verificável.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-130">SAFE and EXTERNAL_ACCESS assemblies can contain only code that is verifiably type-safe.</span></span> <span data-ttu-id="ba8bb-131">Isso significa que esses assemblies só podem acessar classes por pontos bem definido de entrada que sejam válidos para a definição de tipo.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-131">This means that these assemblies can only access classes through well-defined entry points that are valid for the type definition.</span></span> <span data-ttu-id="ba8bb-132">Portanto, eles não podem acessar arbitrariamente buffers de memória não pertencentes ao código.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-132">Therefore, they cannot arbitrarily access memory buffers not owned by the code.</span></span> <span data-ttu-id="ba8bb-133">Adicionalmente, eles não podem executar operações que poderiam ter um efeito adverso na robustez do processo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba8bb-133">Additionally, they cannot perform operations that might have an adverse effect on the robustness of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="ba8bb-134">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="ba8bb-134">UNSAFE</span></span>  
 <span data-ttu-id="ba8bb-135">UNSAFE concede aos assemblies acesso irrestrito aos recursos, dentro e fora do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba8bb-135">UNSAFE gives assemblies unrestricted access to resources, both within and outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ba8bb-136">Código executado em um assembly UNSAFE pode chamar código não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-136">Code that is running from within an UNSAFE assembly can call unmanaged code.</span></span>  
  
 <span data-ttu-id="ba8bb-137">Além disso, especificando UNSAFE permite que o código no assembly execute operações consideradas como tipo inseguro pelo verificador CLR.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-137">Also, specifying UNSAFE allows for the code in the assembly to perform operations that are considered type-unsafe by the CLR verifier.</span></span> <span data-ttu-id="ba8bb-138">Essas operações podem potencialmente acessar buffers de memória no espaço de processo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de uma maneira descontrolada.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-138">These operations can potentially access memory buffers in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process space in an uncontrolled manner.</span></span> <span data-ttu-id="ba8bb-139">Assemblies UNSAFE também podem potencialmente subverter o sistema de segurança do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou do CLR.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-139">UNSAFE assemblies can also potentially subvert the security system of either [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the common language runtime.</span></span> <span data-ttu-id="ba8bb-140">Somente permissões UNSAFE devem ser concedidas a assemblies altamente confiáveis por desenvolvedores ou administradores experientes.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-140">UNSAFE permissions should be granted only to highly trusted assemblies by experienced developers or administrators.</span></span> <span data-ttu-id="ba8bb-141">Somente os membros da função de servidor fixa **sysadmin** podem criar assemblies não seguros.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-141">Only members of the **sysadmin** fixed server role can create UNSAFE assemblies.</span></span>  
  
## <a name="restrictions-on-assemblies"></a><span data-ttu-id="ba8bb-142">Restrições em assemblies</span><span class="sxs-lookup"><span data-stu-id="ba8bb-142">Restrictions on Assemblies</span></span>  
 <span data-ttu-id="ba8bb-143">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] coloca certas restrições em código gerenciado em assemblies para verificar se eles podem ser executados de uma maneira segura e evolutiva.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-143">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] puts certain restrictions on managed code in assemblies to make sure that they can run in a reliable and scalable manner.</span></span> <span data-ttu-id="ba8bb-144">Isso significa que não são permitidas certas operações que podem comprometer a robustez do servidor em assemblies SAFE e EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-144">This means that certain operations that can compromise the robustness of the server are not permitted in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
### <a name="disallowed-custom-attributes"></a><span data-ttu-id="ba8bb-145">Atributos personalizados não permitidos</span><span class="sxs-lookup"><span data-stu-id="ba8bb-145">Disallowed Custom Attributes</span></span>  
 <span data-ttu-id="ba8bb-146">Assemblies não podem ser anotados com os seguintes atributos personalizados:</span><span class="sxs-lookup"><span data-stu-id="ba8bb-146">Assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.ContextStaticAttribute  
System.MTAThreadAttribute  
System.Runtime.CompilerServices.MethodImplAttribute  
System.Runtime.CompilerServices.CompilationRelaxationsAttribute  
System.Runtime.Remoting.Contexts.ContextAttribute  
System.Runtime.Remoting.Contexts.SynchronizationAttribute  
System.Runtime.InteropServices.DllImportAttribute   
System.Security.Permissions.CodeAccessSecurityAttribute  
System.STAThreadAttribute  
System.ThreadStaticAttribute  
```  
  
 <span data-ttu-id="ba8bb-147">Adicionalmente, não podem ser anotados assemblies SAFE e EXTERNAL_ACCESS com os seguintes atributos personalizados:</span><span class="sxs-lookup"><span data-stu-id="ba8bb-147">Additionally, SAFE and EXTERNAL_ACCESS assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.Security.SuppressUnmanagedCodeSecurityAttribute  
System.Security.UnverifiableCodeAttribute  
```  
  
### <a name="disallowed-net-framework-apis"></a><span data-ttu-id="ba8bb-148">APIs não permitidas do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ba8bb-148">Disallowed .NET Framework APIs</span></span>  
 <span data-ttu-id="ba8bb-149">Qualquer [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API que esteja anotada com um dos **HostProtectionAttributes** não permitidos não pode ser chamada de assemblies seguros e EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-149">Any [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API that is annotated with one of the disallowed **HostProtectionAttributes** cannot be called from SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
```  
eSelfAffectingProcessMgmt  
eSelfAffectingThreading  
eSynchronization  
eSharedState   
eExternalProcessMgmt  
eExternalThreading  
eSecurityInfrastructure  
eMayLeakOnAbort  
eUI  
```  
  
### <a name="supported-net-framework-assemblies"></a><span data-ttu-id="ba8bb-150">Assemblies .NET Framework suportados</span><span class="sxs-lookup"><span data-stu-id="ba8bb-150">Supported .NET Framework Assemblies</span></span>  
 <span data-ttu-id="ba8bb-151">Qualquer assembly referenciado por seu assembly personalizado deve ser carregado no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-151">Any assembly that is referenced by your custom assembly must be loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using CREATE ASSEMBLY.</span></span> <span data-ttu-id="ba8bb-152">Os seguintes assemblies do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] já estão carregados no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e, portanto, podem ser consultados por assemblies personalizados sem ter que usar CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="ba8bb-152">The following [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assemblies are already loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and, therefore, can be referenced by custom assemblies without having to use CREATE ASSEMBLY.</span></span>  
  
```  
custommarshallers.dll  
Microsoft.visualbasic.dll  
Microsoft.visualc.dll  
mscorlib.dll  
system.data.dll  
System.Data.SqlXml.dll  
system.dll  
system.security.dll  
system.web.services.dll  
system.xml.dll  
System.Transactions  
System.Data.OracleClient  
System.Configuration  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba8bb-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ba8bb-153">See Also</span></span>  
 <span data-ttu-id="ba8bb-154">[Assemblies &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="ba8bb-154">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 [<span data-ttu-id="ba8bb-155">Segurança da integração CLR</span><span class="sxs-lookup"><span data-stu-id="ba8bb-155">CLR Integration Security</span></span>](security/clr-integration-security.md)  
  
  
