---
title: Arquivos e números de versão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, versions
- components [SMO]
- files [SMO], components
- SMO [SQL Server], versions
- versions [SMO]
ms.assetid: 510907b6-e7a9-41bd-b892-d6d99a5118e1
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1a7286f15af28f97e488b8b40fd745a0d320108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573914"
---
# <a name="files-and-version-numbers"></a><span data-ttu-id="e13ac-102">Arquivos e números de versão</span><span class="sxs-lookup"><span data-stu-id="e13ac-102">Files and Version Numbers</span></span>
  <span data-ttu-id="e13ac-103">Todos os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componentes do SMO (Management Objects) necessários são instalados como parte de uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cliente ou do servidor.</span><span class="sxs-lookup"><span data-stu-id="e13ac-103">All required [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) components are installed as part of an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client or server.</span></span> <span data-ttu-id="e13ac-104">SMO é implementado em vários assemblies gerenciados.</span><span class="sxs-lookup"><span data-stu-id="e13ac-104">SMO is implemented in several managed assemblies.</span></span> <span data-ttu-id="e13ac-105">Você pode desenvolver aplicativos SMO em um cliente ou um servidor.</span><span class="sxs-lookup"><span data-stu-id="e13ac-105">You can develop SMO applications on either a client or a server.</span></span>  
  
|<span data-ttu-id="e13ac-106">Diretório</span><span class="sxs-lookup"><span data-stu-id="e13ac-106">Directory</span></span>|<span data-ttu-id="e13ac-107">Arquivo</span><span class="sxs-lookup"><span data-stu-id="e13ac-107">File</span></span>|<span data-ttu-id="e13ac-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="e13ac-108">Description</span></span>|  
|---------------|----------|-----------------|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="e13ac-109">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="e13ac-109">Microsoft.SqlServer.ConnectionInfo.dll</span></span>|<span data-ttu-id="e13ac-110">Contém suporte para conexão a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e13ac-110">Contains support for connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="e13ac-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span><span class="sxs-lookup"><span data-stu-id="e13ac-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span></span>|<span data-ttu-id="e13ac-112">Contém suporte para programação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span><span class="sxs-lookup"><span data-stu-id="e13ac-112">Contains support for programming the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span></span> <span data-ttu-id="e13ac-113">Só é necessário em programas que acessam o Service Broker.</span><span class="sxs-lookup"><span data-stu-id="e13ac-113">This is required only in programs that access the Service Broker.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="e13ac-114">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="e13ac-114">Microsoft.SqlServer.Smo.dll</span></span>|<span data-ttu-id="e13ac-115">Contém o a maioria das classes SMO.</span><span class="sxs-lookup"><span data-stu-id="e13ac-115">Contains the most of the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="e13ac-116">Microsoft.SqlServer.SmoExtended.dll</span><span class="sxs-lookup"><span data-stu-id="e13ac-116">Microsoft.SqlServer.SmoExtended.dll</span></span><br /><br /> <span data-ttu-id="e13ac-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="e13ac-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span><br /><br /> <span data-ttu-id="e13ac-118">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="e13ac-118">Microsoft.SqlServer.SqlEnum.dll</span></span>|<span data-ttu-id="e13ac-119">Contém suporte para as classes SMO.</span><span class="sxs-lookup"><span data-stu-id="e13ac-119">Contains support for the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="e13ac-120">Microsoft.SqlServer.WmiEnum.dll</span><span class="sxs-lookup"><span data-stu-id="e13ac-120">Microsoft.SqlServer.WmiEnum.dll</span></span>|<span data-ttu-id="e13ac-121">Contém as classes de Provedor WMI (Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="e13ac-121">Contains the Windows Management Instrumentation (WMI) Provider classes.</span></span> <span data-ttu-id="e13ac-122">Só é necessário para programas que usam as classes de Provedor WMI.</span><span class="sxs-lookup"><span data-stu-id="e13ac-122">This is required only for programs that use the WMI Provider classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="e13ac-123">Microsoft.SqlServer.RegSvrEnum.dll</span><span class="sxs-lookup"><span data-stu-id="e13ac-123">Microsoft.SqlServer.RegSvrEnum.dll</span></span>|<span data-ttu-id="e13ac-124">Contém as classes de Servidor Registrado.</span><span class="sxs-lookup"><span data-stu-id="e13ac-124">Contains the Registered Server classes.</span></span> <span data-ttu-id="e13ac-125">Só é necessário para programas que usam as classes de Servidor Registrado.</span><span class="sxs-lookup"><span data-stu-id="e13ac-125">This is required only for programs that use the Registered Server classes.</span></span>|  
  
  
