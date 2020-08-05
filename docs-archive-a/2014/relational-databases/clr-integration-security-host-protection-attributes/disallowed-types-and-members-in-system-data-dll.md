---
title: Tipos e membros não permitidos em System.Data.dll | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- common language runtime [SQL Server], host protection attributes
ms.assetid: ee5f55e9-fbef-401a-be18-a2e5873c8720
author: rothja
ms.author: jroth
ms.openlocfilehash: cd62f6f0a90bd167f20a33f8de749acc982f39b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572109"
---
# <a name="disallowed-types-and-members-in-systemdatadll"></a><span data-ttu-id="c9b7e-102">Tipos e membros não permitidos em System.Data.dll</span><span class="sxs-lookup"><span data-stu-id="c9b7e-102">Disallowed Types and Members in System.Data.dll</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="c9b7e-103">a programação comum de integração de linguagem (CLR) não permite o uso de um tipo ou membro que tenha um `HostProtectionAttribute` que especifique uma `System.Security.Permissions.HostProtectionResource` enumeração com um valor de,,,,, `ExternalProcessMgmt` `ExternalThreading` `MayLeakOnAbort` `SecurityInfrastructure` `SelfAffectingProcessMgmnt` `SelfAffectingThreading` , **SharedState**, `Synchronization` ou `UI` .</span><span class="sxs-lookup"><span data-stu-id="c9b7e-103">common language integration (CLR) programming disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, **SharedState**, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="c9b7e-104">A tabela a seguir lista os membros e os tipos do assembly System.Data.dll cujos valores de HPA (atributo de proteção de host) não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c9b7e-104">The following table lists the members and types of the System.Data.dll assembly whose Host Protection Attribute (HPA) values are disallowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9b7e-105">Esta lista foi gerada dos assembly com suporte.</span><span class="sxs-lookup"><span data-stu-id="c9b7e-105">This list was generated from the supported assemblies.</span></span> <span data-ttu-id="c9b7e-106">Para obter mais informações, consulte [bibliotecas de .NET Framework com suporte](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="c9b7e-106">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
|<span data-ttu-id="c9b7e-107">Tipo ou membro</span><span class="sxs-lookup"><span data-stu-id="c9b7e-107">Type or Member</span></span>|<span data-ttu-id="c9b7e-108">Valor(es) de HPA</span><span class="sxs-lookup"><span data-stu-id="c9b7e-108">HPA Value(s)</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="c9b7e-109">System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery ()</span><span class="sxs-lookup"><span data-stu-id="c9b7e-109">System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery()</span></span>|<span data-ttu-id="c9b7e-110">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="c9b7e-110">ExternalThreading</span></span>|  
|<span data-ttu-id="c9b7e-111">System.Data.SqlClient.SqlCommand.BeginExecuteReader()</span><span class="sxs-lookup"><span data-stu-id="c9b7e-111">System.Data.SqlClient.SqlCommand.BeginExecuteReader()</span></span>|<span data-ttu-id="c9b7e-112">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="c9b7e-112">ExternalThreading</span></span>|  
|<span data-ttu-id="c9b7e-113">System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()</span><span class="sxs-lookup"><span data-stu-id="c9b7e-113">System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()</span></span>|<span data-ttu-id="c9b7e-114">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="c9b7e-114">ExternalThreading</span></span>|  
|<span data-ttu-id="c9b7e-115">System.Data.SqlClient.SqlDependency..ctor ()</span><span class="sxs-lookup"><span data-stu-id="c9b7e-115">System.Data.SqlClient.SqlDependency..ctor()</span></span>|<span data-ttu-id="c9b7e-116">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="c9b7e-116">ExternalThreading</span></span>|  
|<span data-ttu-id="c9b7e-117">System.Data.SqlClient.SqlDependency.Start ()</span><span class="sxs-lookup"><span data-stu-id="c9b7e-117">System.Data.SqlClient.SqlDependency.Start()</span></span>|<span data-ttu-id="c9b7e-118">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="c9b7e-118">ExternalThreading</span></span>|  
|<span data-ttu-id="c9b7e-119">System.Data.SqlClient.SqlDependency.Stop()</span><span class="sxs-lookup"><span data-stu-id="c9b7e-119">System.Data.SqlClient.SqlDependency.Stop()</span></span>|<span data-ttu-id="c9b7e-120">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="c9b7e-120">ExternalThreading</span></span>|  
|<span data-ttu-id="c9b7e-121">System.Data.TypedDataSetGenerator</span><span class="sxs-lookup"><span data-stu-id="c9b7e-121">System.Data.TypedDataSetGenerator</span></span>|<span data-ttu-id="c9b7e-122">SharedState, Sincronização</span><span class="sxs-lookup"><span data-stu-id="c9b7e-122">SharedState, Synchronization</span></span>|  
|<span data-ttu-id="c9b7e-123">System.Xml.XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="c9b7e-123">System.Xml.XmlDataDocument</span></span>|<span data-ttu-id="c9b7e-124">Sincronização</span><span class="sxs-lookup"><span data-stu-id="c9b7e-124">Synchronization</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9b7e-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9b7e-125">See Also</span></span>  
 <span data-ttu-id="c9b7e-126">[Atributos de proteção do host e programação de integração CLR](host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="c9b7e-126">[Host Protection Attributes and CLR Integration Programming](host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 <span data-ttu-id="c9b7e-127">[Tipos e membros não permitidos em Microsoft.VisualBasic.dll](disallowed-types-and-members-in-microsoft-visualbasic-dll.md) </span><span class="sxs-lookup"><span data-stu-id="c9b7e-127">[Disallowed Types and Members in Microsoft.VisualBasic.dll](disallowed-types-and-members-in-microsoft-visualbasic-dll.md) </span></span>  
 <span data-ttu-id="c9b7e-128">[Tipos e membros não permitidos em mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span><span class="sxs-lookup"><span data-stu-id="c9b7e-128">[Disallowed Types and Members in mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span></span>  
 <span data-ttu-id="c9b7e-129">[Tipos e membros não permitidos em System.dll](disallowed-types-and-members-in-system-dll.md) </span><span class="sxs-lookup"><span data-stu-id="c9b7e-129">[Disallowed Types and Members in System.dll](disallowed-types-and-members-in-system-dll.md) </span></span>  
 [<span data-ttu-id="c9b7e-130">Tipos e membros desaprovados no System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="c9b7e-130">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
  
  
