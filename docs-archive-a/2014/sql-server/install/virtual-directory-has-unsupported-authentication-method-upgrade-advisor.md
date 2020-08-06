---
title: O diretório virtual tem um método de autenticação sem suporte (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 216eca6f-9a66-42e1-aa54-dcf99cec9f7d
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 67b1c027b8ed020f65fdea7c093f6d5454f02c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573410"
---
# <a name="virtual-directory-has-unsupported-authentication-method-upgrade-advisor"></a><span data-ttu-id="d9d4f-102">Diretório virtual com método de autenticação sem suporte (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="d9d4f-102">Virtual directory has unsupported authentication method (Upgrade Advisor)</span></span>
  <span data-ttu-id="d9d4f-103">O Supervisor de Atualização detectou um método de autenticação sem suporte no diretório virtual do Gerenciador de Relatórios ou do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d9d4f-103">Upgrade Advisor detected an unsupported authentication method on the Report Manager or report server virtual directory.</span></span> <span data-ttu-id="d9d4f-104">Os métodos de autenticação para os quais a atualização não oferece suporte incluem Anônimo, Digest e .NET Passport.</span><span class="sxs-lookup"><span data-stu-id="d9d4f-104">Authentication methods that are not supported by upgrade include Anonymous, Digest, and .NET Passport.</span></span>  
  
||  
|-|  
|<span data-ttu-id="d9d4f-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="d9d4f-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="d9d4f-106">Componente</span><span class="sxs-lookup"><span data-stu-id="d9d4f-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="d9d4f-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="d9d4f-107">Description</span></span>  
 <span data-ttu-id="d9d4f-108">A instalação não pode atualizar uma instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que use um dos métodos de autenticação a seguir</span><span class="sxs-lookup"><span data-stu-id="d9d4f-108">Setup cannot upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that uses one of the following authentication methods</span></span>  
  
-   <span data-ttu-id="d9d4f-109">Anônima</span><span class="sxs-lookup"><span data-stu-id="d9d4f-109">Anonymous</span></span>  
  
-   <span data-ttu-id="d9d4f-110">Digest</span><span class="sxs-lookup"><span data-stu-id="d9d4f-110">Digest</span></span>  
  
-   <span data-ttu-id="d9d4f-111">.NET Passport</span><span class="sxs-lookup"><span data-stu-id="d9d4f-111">.NET Passport</span></span>  
  
 <span data-ttu-id="d9d4f-112">Para continuar, você pode modificar o método de autenticação especificado para os diretórios virtuais do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no Internet Information Services (IIS) ou migrar sua instalação.</span><span class="sxs-lookup"><span data-stu-id="d9d4f-112">To continue, you can either modify the Authentication method that is specified for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] virtual directories in Internet Information Services (IIS), or you can migrate your installation.</span></span> <span data-ttu-id="d9d4f-113">Para obter mais informações sobre como migrar sua instalação, consulte os Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9d4f-113">For more information about migrating your installation, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="d9d4f-114">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="d9d4f-114">Corrective Action</span></span>  
 <span data-ttu-id="d9d4f-115">Para continuar com atualização, modifique o método de autenticação do IIS dos diretórios virtuais do ReportServer e Reports.</span><span class="sxs-lookup"><span data-stu-id="d9d4f-115">To continue with upgrade, modify the Authentication method in IIS for the ReportServer and Reports virtual directories.</span></span> <span data-ttu-id="d9d4f-116">Para obter mais informações sobre como modificar os métodos de autenticação no IIS, consulte a documentação do IIS.</span><span class="sxs-lookup"><span data-stu-id="d9d4f-116">For more information about modifying Authentication methods in IIS, see the IIS documentation.</span></span> <span data-ttu-id="d9d4f-117">Depois que você modificar o método de autenticação dos diretórios virtuais do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], execute novamente o Supervisor de Atualização para confirmar que não existe nenhum outro problema de atualização.</span><span class="sxs-lookup"><span data-stu-id="d9d4f-117">After you modify the Authentication method for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] virtual directories, re-run Upgrade Advisor to confirm that there are no other upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9d4f-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d9d4f-118">See Also</span></span>  
 [<span data-ttu-id="d9d4f-119">Problemas de atualização do Reporting Services &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="d9d4f-119">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
