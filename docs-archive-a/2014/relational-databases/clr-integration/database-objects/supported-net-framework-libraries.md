---
title: Bibliotecas de .NET Framework com suporte | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], .NET Framework libraries
- .NET Framework [CLR Integration]
ms.assetid: 417544ff-c25c-496e-add4-2f278f8a4911
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f92e3eadccc869452cf35534f786724c8e259a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568633"
---
# <a name="supported-net-framework-libraries"></a><span data-ttu-id="0d87a-102">Bibliotecas do .NET Framework compatíveis</span><span class="sxs-lookup"><span data-stu-id="0d87a-102">Supported .NET Framework Libraries</span></span>
  <span data-ttu-id="0d87a-103">Com o CLR (common language runtime) hospedado no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], você pode criar procedimentos armazenados, gatilhos, funções definidas pelo usuário, tipos definidos pelo usuário e agregações definidas pelo usuário em código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="0d87a-103">With the common language runtime (CLR) hosted in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="0d87a-104">Com a funcionalidade contida nas bibliotecas de classe do .NET Framework, você tem acesso a classes pré-criadas que fornecem recursos de manipulação de cadeia de caracteres, operações matemáticas avançadas, acesso a arquivos, criptografia, e mais.</span><span class="sxs-lookup"><span data-stu-id="0d87a-104">With the functionality found in the .NET Framework class libraries, you have access to pre-built classes that provide functionality for string manipulation, advanced math operations, file access, cryptography, and more.</span></span> <span data-ttu-id="0d87a-105">Essas classes podem ser acessadas de qualquer procedimento armazenado gerenciado, tipo definido pelo usuário, gatilho, função definida pelo usuário ou agregação definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="0d87a-105">These classes can be accessed from any managed stored procedure, user-defined type, trigger, user-defined function, or user-defined aggregate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d87a-106">Se você atender ou atualizar assemblies sem suporte no GAC (cache de assembly global), seu [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d87a-106">If you service or upgrade unsupported assemblies in the global assembly cache (GAC), your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0d87a-107">Se um assembly existir em uma [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] integração CLR.</span><span class="sxs-lookup"><span data-stu-id="0d87a-107">If an assembly exists both in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span> <span data-ttu-id="0d87a-108">Se você reparar ou atualizar qualquer assembly no GAC que também está registrado no banco de dados, incluindo os assemblies do .NET Framework sem suporte, verifique se também reparou ou atualizou a cópia do assembly nos bancos de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com a instrução `ALTER ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="0d87a-108">If you service or upgrade any assemblies in the GAC that are also registered in the database, including unsupported .NET Framework assemblies, make sure to also service or upgrade the copy of the assembly inside your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases with the `ALTER ASSEMBLY` statement.</span></span> <span data-ttu-id="0d87a-109">Para obter mais informações, consulte o [artigo 949080 da base de dados de conhecimento](https://support.microsoft.com/kb/949080).</span><span class="sxs-lookup"><span data-stu-id="0d87a-109">For more information, see [Knowledge Base article 949080](https://support.microsoft.com/kb/949080).</span></span>  
  
## <a name="supported-libraries"></a><span data-ttu-id="0d87a-110">Bibliotecas com suporte</span><span class="sxs-lookup"><span data-stu-id="0d87a-110">Supported Libraries</span></span>  
 <span data-ttu-id="0d87a-111">A partir [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] do tem uma lista de bibliotecas de .NET Framework com suporte, que foram testadas para garantir que elas atendam aos padrões de confiabilidade e segurança para interação com as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cargas diretamente do GAC (cache de assembly global).</span><span class="sxs-lookup"><span data-stu-id="0d87a-111">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] has a list of supported .NET Framework libraries, which have been tested to ensure that they meet reliability and security standards for interaction with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] loads them directly from the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="0d87a-112">As bibliotecas/namespaces suportados pela integração CLR no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] são:</span><span class="sxs-lookup"><span data-stu-id="0d87a-112">The libraries/namespaces supported by CLR integration in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are:</span></span>  
  
-   <span data-ttu-id="0d87a-113">CustomMarshalers</span><span class="sxs-lookup"><span data-stu-id="0d87a-113">CustomMarshalers</span></span>  
  
-   <span data-ttu-id="0d87a-114">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="0d87a-114">Microsoft.VisualBasic</span></span>  
  
-   <span data-ttu-id="0d87a-115">Microsoft.VisualC</span><span class="sxs-lookup"><span data-stu-id="0d87a-115">Microsoft.VisualC</span></span>  
  
-   <span data-ttu-id="0d87a-116">mscorlib</span><span class="sxs-lookup"><span data-stu-id="0d87a-116">mscorlib</span></span>  
  
-   <span data-ttu-id="0d87a-117">Sistema</span><span class="sxs-lookup"><span data-stu-id="0d87a-117">System</span></span>  
  
-   <span data-ttu-id="0d87a-118">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="0d87a-118">System.Configuration</span></span>  
  
-   <span data-ttu-id="0d87a-119">System.Data</span><span class="sxs-lookup"><span data-stu-id="0d87a-119">System.Data</span></span>  
  
-   <span data-ttu-id="0d87a-120">System.Data.OracleClient</span><span class="sxs-lookup"><span data-stu-id="0d87a-120">System.Data.OracleClient</span></span>  
  
-   <span data-ttu-id="0d87a-121">System.Data.SqlXml</span><span class="sxs-lookup"><span data-stu-id="0d87a-121">System.Data.SqlXml</span></span>  
  
-   <span data-ttu-id="0d87a-122">System.Deployment</span><span class="sxs-lookup"><span data-stu-id="0d87a-122">System.Deployment</span></span>  
  
-   <span data-ttu-id="0d87a-123">System.Security</span><span class="sxs-lookup"><span data-stu-id="0d87a-123">System.Security</span></span>  
  
-   <span data-ttu-id="0d87a-124">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="0d87a-124">System.Transactions</span></span>  
  
-   <span data-ttu-id="0d87a-125">System.Web.Services</span><span class="sxs-lookup"><span data-stu-id="0d87a-125">System.Web.Services</span></span>  
  
-   <span data-ttu-id="0d87a-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="0d87a-126">System.Xml</span></span>  
  
-   <span data-ttu-id="0d87a-127">System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="0d87a-127">System.Core.dll</span></span>  
  
-   <span data-ttu-id="0d87a-128">System.Xml.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="0d87a-128">System.Xml.Linq.dll</span></span>  
  
## <a name="unsupported-libraries"></a><span data-ttu-id="0d87a-129">Bibliotecas sem-suporte</span><span class="sxs-lookup"><span data-stu-id="0d87a-129">Unsupported Libraries</span></span>  
 <span data-ttu-id="0d87a-130">As bibliotecas sem-suporte ainda podem ser chamadas de seus procedimentos armazenados gerenciados, gatilhos, funções definidas pelo usuário, tipos definidos pelo usuário e agregações definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="0d87a-130">Unsupported libraries can still be called from your managed stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates.</span></span> <span data-ttu-id="0d87a-131">A biblioteca sem-suporte deve ser registrada primeiro no banco de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], usando a instrução `CREATE ASSEMBLY`, antes de poder ser usada no seu código.</span><span class="sxs-lookup"><span data-stu-id="0d87a-131">The unsupported library must first be registered in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, using the `CREATE ASSEMBLY` statement, before it can be used in your code.</span></span> <span data-ttu-id="0d87a-132">Qualquer biblioteca sem-suporte que é registrada e executada no servidor deveria ser examinada e testada para fins de segurança e confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="0d87a-132">Any unsupported library that is registered and run on the server should be reviewed and tested for security and reliability.</span></span>  
  
 <span data-ttu-id="0d87a-133">Por exemplo, o namespace `System.DirectoryServices` não é suportado.</span><span class="sxs-lookup"><span data-stu-id="0d87a-133">For example, the `System.DirectoryServices` namespace is not supported.</span></span> <span data-ttu-id="0d87a-134">Você deve registrar o assembly System.DirectoryServices.dll com permissões `UNSAFE` antes de poder chamá-lo do seu código.</span><span class="sxs-lookup"><span data-stu-id="0d87a-134">You must register the System.DirectoryServices.dll assembly with `UNSAFE` permissions before you can call it from your code.</span></span> <span data-ttu-id="0d87a-135">A permissão `UNSAFE` é necessária porque classes no namespace `System.DirectoryServices` não satisfazem aos requisitos para `SAFE` ou `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="0d87a-135">The `UNSAFE` permission is necessary because classes in the `System.DirectoryServices` namespace do not meet the requirements for `SAFE` or `EXTERNAL_ACCESS`.</span></span> <span data-ttu-id="0d87a-136">Para obter mais informações, consulte [restrições de modelo de programação de integração CLR](clr-integration-programming-model-restrictions.md) e segurança de acesso a código de [integração CLR](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="0d87a-136">For more information, see [CLR Integration Programming Model Restrictions](clr-integration-programming-model-restrictions.md) and [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d87a-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0d87a-137">See Also</span></span>  
 <span data-ttu-id="0d87a-138">[Criando um assembly](../assemblies/creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="0d87a-138">[Creating an Assembly](../assemblies/creating-an-assembly.md) </span></span>  
 <span data-ttu-id="0d87a-139">[Segurança de acesso ao código de integração CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="0d87a-139">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 [<span data-ttu-id="0d87a-140">Restrições do modelo de programação da Integração CLR</span><span class="sxs-lookup"><span data-stu-id="0d87a-140">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
  
  
