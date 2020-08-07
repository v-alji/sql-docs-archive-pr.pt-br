---
title: Desenvolvimento seguro (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- development security [Reporting Services]
- security [Reporting Services], development
- security [Reporting Services], strategies
ms.assetid: 12161a6c-b93b-4312-9d27-0c922561eb9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ba284b9013c5da6b03cce06ec72deccb045cfad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584013"
---
# <a name="secure-development-reporting-services"></a><span data-ttu-id="3a3c0-102">Desenvolvimento seguro (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="3a3c0-102">Secure Development (Reporting Services)</span></span>
  <span data-ttu-id="3a3c0-103">O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] fornece um sistema de segurança robusto que pode executar o código em contextos de segurança altamente restritos definidos pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="3a3c0-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a robust security system that can run code in tightly constrained, administrator-defined security contexts.</span></span> <span data-ttu-id="3a3c0-104">O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] usa o sistema de segurança do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], conhecido como segurança de acesso a código (ou segurança baseada em evidência).</span><span class="sxs-lookup"><span data-stu-id="3a3c0-104">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] security system, known as code access security (or evidence-based security).</span></span> <span data-ttu-id="3a3c0-105">Na segurança de acesso do código, um usuário pode ser confiável para acessar um recurso, mas se o código executado pelo usuário não for confiável, o acesso ao recurso será negado.</span><span class="sxs-lookup"><span data-stu-id="3a3c0-105">Under code access security, a user may be trusted to access a resource, but if the code the user executes is not trusted, access to the resource will be denied.</span></span>  
  
 <span data-ttu-id="3a3c0-106">A segurança baseada em código, ao contrário de usuários específicos, permite que a segurança seja expressa para assemblies ou dados personalizados, entrega, criação e extensões de segurança desenvolvidos para o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a3c0-106">Security based on code, as opposed to specific users, permits security to be expressed for custom assemblies or data, delivery, rendering, and security extensions that you develop for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="3a3c0-107">O código de extensão pode ser executado por qualquer número de usuários do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], todos conhecidos durante o desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="3a3c0-107">Your extension code may be executed by any number of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] users, all of whom are unknown at development time.</span></span> <span data-ttu-id="3a3c0-108">Os assemblies ou extensões personalizados que você desenvolve exigem políticas de segurança específicas no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a3c0-108">The custom assemblies or extensions that you develop require specific security policies in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="3a3c0-109">Essas políticas de segurança são representadas como tipos no [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a3c0-109">These security policies are represented as types in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="3a3c0-110">Para obter mais informações sobre segurança de acesso do código, consulte "Segurança de acesso do código" na documentação do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a3c0-110">For a more information about code access security, see "Code Access Security" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a3c0-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3a3c0-111">In This Section</span></span>  
 [<span data-ttu-id="3a3c0-112">Segurança de acesso do código no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3a3c0-112">Code Access Security in Reporting Services</span></span>](code-access-security-in-reporting-services.md)  
 <span data-ttu-id="3a3c0-113">Apresenta a segurança de acesso do código e a configuração de políticas para extensões e assemblies personalizados no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a3c0-113">Introduces code access security and policy configuration for custom assemblies and extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="3a3c0-114">Compreender as políticas de segurança</span><span class="sxs-lookup"><span data-stu-id="3a3c0-114">Understanding Security Policies</span></span>](understanding-security-policies.md)  
 <span data-ttu-id="3a3c0-115">Descreve os vários tipos de assembly no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] e como a segurança de acesso do código afeta permissões de código.</span><span class="sxs-lookup"><span data-stu-id="3a3c0-115">Describes the various assembly types in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] and how code access security affects code permissions.</span></span>  
  
 [<span data-ttu-id="3a3c0-116">Usar arquivos de política de segurança do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3a3c0-116">Using Reporting Services Security Policy Files</span></span>](using-reporting-services-security-policy-files.md)  
 <span data-ttu-id="3a3c0-117">Descreve os diferentes componentes do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] e os arquivos de configuração de política correspondentes.</span><span class="sxs-lookup"><span data-stu-id="3a3c0-117">Describes the different [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] components and the corresponding policy configuration files.</span></span>  
  
  
