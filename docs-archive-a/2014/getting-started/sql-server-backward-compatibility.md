---
title: Compatibilidade com versões anteriores do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ac47cb74-5578-417d-bcef-f970d9527705
author: rothja
ms.author: jroth
ms.openlocfilehash: a4d38041ce4daa12911dc706d382460324931c90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680039"
---
# <a name="sql-server-backward-compatibility"></a><span data-ttu-id="cb547-102">Compatibilidade com versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb547-102">SQL Server Backward Compatibility</span></span>
  <span data-ttu-id="cb547-103">Os tópicos da seção sobre compatibilidade com versões anteriores descrevem alterações no comportamento do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] entre versões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb547-103">Topics in the backward compatibility section describe changes in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] behavior between versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cb547-104">Os recursos incluídos nesta área de tópico incluem programabilidade de dados, ferramentas de configuração de área da superfície, instalação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , serviços do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e outras amplas alterações de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="cb547-104">Features included in this topic area include data programmability, surface area configuration tools, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] services, and other broad functionality changes.</span></span>  
  
|<span data-ttu-id="cb547-105">Tópico</span><span class="sxs-lookup"><span data-stu-id="cb547-105">Topic</span></span>|<span data-ttu-id="cb547-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb547-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cb547-107">Recursos do SQL Server obsoletos no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="cb547-107">Deprecated SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/deprecated-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="cb547-108">Recursos preteridos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nesta versão.</span><span class="sxs-lookup"><span data-stu-id="cb547-108">Deprecated [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] features in this release.</span></span> <span data-ttu-id="cb547-109">Este tópico abrange a configuração do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e a funcionalidade de Instalação.</span><span class="sxs-lookup"><span data-stu-id="cb547-109">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
|[<span data-ttu-id="cb547-110">Recursos do SQL Server descontinuados no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="cb547-110">Discontinued SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/discontinued-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="cb547-111">Funcionalidade do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] descontinuada nesta versão.</span><span class="sxs-lookup"><span data-stu-id="cb547-111">Discontinued [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] functionality in this release.</span></span> <span data-ttu-id="cb547-112">Este tópico abrange a configuração do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e a funcionalidade de Instalação.</span><span class="sxs-lookup"><span data-stu-id="cb547-112">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
|[<span data-ttu-id="cb547-113">Alterações recentes em recursos do SQL Server no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="cb547-113">Breaking Changes to SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/breaking-changes-to-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="cb547-114">Alterações que podem exigir alterações em aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cb547-114">Changes that might require changes to applications.</span></span> <span data-ttu-id="cb547-115">Este tópico abrange a configuração do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e a funcionalidade de Instalação.</span><span class="sxs-lookup"><span data-stu-id="cb547-115">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
|[<span data-ttu-id="cb547-116">Alterações no comportamento de recursos do SQL Server no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="cb547-116">Behavior Changes to SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/behavior-changes-to-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="cb547-117">Alterações comportamentais em recursos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nesta versão.</span><span class="sxs-lookup"><span data-stu-id="cb547-117">Behavioral  changes to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] features in this release.</span></span> <span data-ttu-id="cb547-118">Este tópico abrange a configuração do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e a funcionalidade de Instalação.</span><span class="sxs-lookup"><span data-stu-id="cb547-118">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb547-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cb547-119">See Also</span></span>  
 [<span data-ttu-id="cb547-120">Compatibilidade com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="cb547-120">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
  
  
