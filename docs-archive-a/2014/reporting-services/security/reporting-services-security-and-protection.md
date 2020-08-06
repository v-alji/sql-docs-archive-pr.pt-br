---
title: Segurança e proteção do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- security [Reporting Services]
- Reporting Services, security
ms.assetid: 270075c5-bf12-4467-a775-abbda3d954a5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0f8c7a4186c5236260fb27d8de107ce8c97bd363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582810"
---
# <a name="reporting-services-security-and-protection"></a><span data-ttu-id="3d572-102">Segurança e proteção do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3d572-102">Reporting Services Security and Protection</span></span>
  <span data-ttu-id="3d572-103">Você pode usar as informações desta seção para obter informações sobre os recursos de segurança do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d572-103">You can use information in this section to learn about the security features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="3d572-104">Esta seção também explica os modelos de autorização e os provedores de autenticação com suporte no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d572-104">This section also explains the authorization models and authentication providers supported in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="extended-protection-for-authentication"></a><span data-ttu-id="3d572-105">Proteção Estendida para Autenticação</span><span class="sxs-lookup"><span data-stu-id="3d572-105">Extended Protection for Authentication</span></span>  
 <span data-ttu-id="3d572-106">A partir do [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], o suporte para Proteção Estendida para Autenticação está disponível.</span><span class="sxs-lookup"><span data-stu-id="3d572-106">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], support for Extended Protection for Authentication is available.</span></span> <span data-ttu-id="3d572-107">O recurso do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte ao uso de associação de canal e associação de serviço para aprimorar a proteção da autenticação.</span><span class="sxs-lookup"><span data-stu-id="3d572-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature supports the use of channel binding and service binding to enhance protection of authentication.</span></span> <span data-ttu-id="3d572-108">Os recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precisam ser usados com um sistema operacional que ofereça suporte à Proteção Estendida.</span><span class="sxs-lookup"><span data-stu-id="3d572-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features need to be used with an operating system that supports Extended Protection.</span></span> <span data-ttu-id="3d572-109">Para obter mais informações, consulte [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3d572-109">For more information, see [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span></span>  
  
## <a name="authentication-and-authorization"></a><span data-ttu-id="3d572-110">Autenticação e autorização</span><span class="sxs-lookup"><span data-stu-id="3d572-110">Authentication and Authorization</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="3d572-111">fornece diferentes tipos de autenticação para aplicativos de usuários e de cliente para autenticação com o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d572-111">provides different authentication types for users and client applications to authenticate with the report server.</span></span> <span data-ttu-id="3d572-112">O uso do tipo certo de autenticação para seu servidor de relatório permite obter o nível adequado de segurança necessário para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d572-112">Using the right authentication type for your report server enables your organization to achieve the appropriate level of security required by your organization.</span></span> <span data-ttu-id="3d572-113">Para obter mais informações, consulte [Authentication with the Report Server](authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="3d572-113">For more information, see [Authentication with the Report Server](authentication-with-the-report-server.md).</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="3d572-114">também utiliza funções e permissões para controlar o acesso de usuários ao conteúdo do catálogo do servidor de relatório (em outras palavras, quem pode acessar o que e como o acesso pode ser feito).</span><span class="sxs-lookup"><span data-stu-id="3d572-114">also employs roles and permissions to control user access to content in the report server catalog (in other words, who can access what, and how s/he can access it).</span></span> <span data-ttu-id="3d572-115">Para obter mais informações, consulte [Funções e permissões &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3d572-115">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3d572-116">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="3d572-116">Related Tasks</span></span>  
  
|<span data-ttu-id="3d572-117">Descrições das tarefas</span><span class="sxs-lookup"><span data-stu-id="3d572-117">Task Descriptions</span></span>|<span data-ttu-id="3d572-118">Links</span><span class="sxs-lookup"><span data-stu-id="3d572-118">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="3d572-119">Configurar o protocolo SSL para proteger conexões de cliente com o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d572-119">Configure the Secure Socket Layer (SSL) to secure client connections to the report server.</span></span>|[<span data-ttu-id="3d572-120">Configurar conexões SSL em um servidor de relatórios do modo nativo</span><span class="sxs-lookup"><span data-stu-id="3d572-120">Configure SSL Connections on a Native Mode Report Server</span></span>](configure-ssl-connections-on-a-native-mode-report-server.md)|  
  
  
