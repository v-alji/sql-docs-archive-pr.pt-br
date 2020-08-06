---
title: Instalar atualizações de serviço do SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 7d6c962b-c8d0-49f7-a2ac-00ad8dca930a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace0fd187386d9a9d96e82f61d1efaa254f08c6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679493"
---
# <a name="install-sql-server-2014-servicing-updates"></a><span data-ttu-id="44a79-102">Instalar atualizações de serviço do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="44a79-102">Install SQL Server 2014 Servicing Updates</span></span>
  <span data-ttu-id="44a79-103">Este tópico fornece informações sobre como instalar atualizações para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44a79-103">This topic provides information about installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="44a79-104">Esta seção fornece informações sobre o seguinte:</span><span class="sxs-lookup"><span data-stu-id="44a79-104">This section provides information about the following:</span></span>  
  
-   <span data-ttu-id="44a79-105">Instalando atualizações para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] durante uma nova instalação</span><span class="sxs-lookup"><span data-stu-id="44a79-105">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] during a new installation</span></span>  
  
-   <span data-ttu-id="44a79-106">Instalando atualizações para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] depois que já tiver sido instalado.</span><span class="sxs-lookup"><span data-stu-id="44a79-106">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed.</span></span>  
  
 <span data-ttu-id="44a79-107">Nós recomendamos que os clientes avaliem e instalem as atualizações mais recentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o mais rápido possível para ter certeza de que os sistemas estejam atualizados com as atualizações de segurança mais recentes.</span><span class="sxs-lookup"><span data-stu-id="44a79-107">We recommend that customers evaluate and install latest [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates in a timely manner to make sure that systems are up-to-date with the most recent security updates.</span></span>  
  
## <a name="installing-updates-for-sscurrent-during-a-new-installation"></a><span data-ttu-id="44a79-108">Instalando atualizações para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] durante uma nova instalação</span><span class="sxs-lookup"><span data-stu-id="44a79-108">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] During a New Installation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="44a79-109">integra as últimas atualizações de produto com a instalação principal de produto, de forma que o produto principal e suas atualizações aplicáveis sejam instalados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="44a79-109">setup integrates the latest product updates with the main product installation so that the main product and its applicable updates are installed at the same time.</span></span> <span data-ttu-id="44a79-110">A atualização de produto pode pesquisar as atualizações aplicáveis de:</span><span class="sxs-lookup"><span data-stu-id="44a79-110">Product Update can search for the applicable updates from:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="44a79-111">Update (atualizar)</span><span class="sxs-lookup"><span data-stu-id="44a79-111">Update</span></span>  
  
-   <span data-ttu-id="44a79-112">Windows Server Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="44a79-112">Windows Server Update Services (WSUS)</span></span>  
  
-   <span data-ttu-id="44a79-113">Uma pasta local</span><span class="sxs-lookup"><span data-stu-id="44a79-113">A local folder</span></span>  
  
-   <span data-ttu-id="44a79-114">Um compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="44a79-114">A network share</span></span>  
  
 <span data-ttu-id="44a79-115">Depois que a Instalação localizar as versões mais recentes das atualizações aplicáveis, ela baixará e integrará essas atualizações com o processo de instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atual.</span><span class="sxs-lookup"><span data-stu-id="44a79-115">After Setup finds the latest versions of the applicable updates, it downloads and integrates them with the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup process.</span></span> <span data-ttu-id="44a79-116">A Atualização de Produto pode incluir uma atualização cumulativa, service pack ou service pack mais atualização cumulativa.</span><span class="sxs-lookup"><span data-stu-id="44a79-116">Product Update can include a cumulative update, service pack, or service pack plus cumulative update.</span></span> <span data-ttu-id="44a79-117">A funcionalidade Atualização de Produto é uma extensão da [funcionalidade de instalação integrada](https://go.microsoft.com/fwlink/?LinkId=219945) que estava disponível no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span><span class="sxs-lookup"><span data-stu-id="44a79-117">Product Update functionality is an extension of the [Slipstream Functionality](https://go.microsoft.com/fwlink/?LinkId=219945) that was available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span></span>  
  
## <a name="installing-updates-for-sscurrent-after-it-has-already-been-installed"></a><span data-ttu-id="44a79-118">Instalando atualizações para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] depois que já tiver sido instalado</span><span class="sxs-lookup"><span data-stu-id="44a79-118">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed</span></span>  
 <span data-ttu-id="44a79-119">Em uma instância instalada do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , recomendamos que você aplique todas as atualizações disponíveis: lançamentos de distribuição geral (atualizações de segurança/crítica GDR), Service Packs (SP), bem como a atualização cumulativa mais recente disponível (cu).</span><span class="sxs-lookup"><span data-stu-id="44a79-119">On an installed instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you apply all available updates: General Distribution Releases (GDR - security/critical updates), Service Packs (SP), as well as the latest available Cumulative Update (CU).</span></span>  
  
 <span data-ttu-id="44a79-120">Dependendo do tipo de versão de serviço, SQL Server atualizações estão disponíveis via Microsoft Update (MU), o centro de download da Microsoft e/ou o servidor de hotfix dos serviços de atendimento ao cliente.</span><span class="sxs-lookup"><span data-stu-id="44a79-120">Depending on the type of servicing release, SQL Server updates are available via Microsoft Update (MU), the Microsoft Download Center, and/or the Customer Support Services hotfix Server.</span></span> <span data-ttu-id="44a79-121">As atualizações de segurança e críticas para SQL Server são fornecidas automaticamente pelo Microsoft Update (para poder ver essas atualizações, você precisa aceitar o MU por meio de Windows Update no painel de controle).</span><span class="sxs-lookup"><span data-stu-id="44a79-121">Security and Critical updates for SQL Server are automatically provided by Microsoft Update (to be able to see these updates you need to opt-in to MU through Windows Update in Control panel).</span></span> <span data-ttu-id="44a79-122">Os service packs estão disponíveis no MU como downloads opcionais/importantes, bem como no centro de download.</span><span class="sxs-lookup"><span data-stu-id="44a79-122">Service Packs are available on MU as Optional/Important downloads as well as the Download Center.</span></span> <span data-ttu-id="44a79-123">As atualizações cumulativas estão disponíveis no Microsoft hotfix Download Server fornecido em CU artigos da base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="44a79-123">Cumulative updates are available on the Microsoft hotfix download server provided in CU Knowledge Base articles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44a79-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44a79-124">See Also</span></span>  
 <span data-ttu-id="44a79-125">[Instale o SQL Server 2014 do assistente de instalação &#40;a instalação&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span><span class="sxs-lookup"><span data-stu-id="44a79-125">[Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span></span>  
 <span data-ttu-id="44a79-126">A [instalação de atualizações do prompt de comando](installing-updates-from-the-command-prompt.md) [adiciona recursos a uma instância do SQL Server 2014 &#40;instalação&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span><span class="sxs-lookup"><span data-stu-id="44a79-126">[Installing updates from the command prompt](installing-updates-from-the-command-prompt.md) [Add Features to an Instance of SQL Server 2014 &#40;Setup&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span></span>  
 [<span data-ttu-id="44a79-127">Remover uma instalação do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="44a79-127">Drop a SQL Server 2014 Installation</span></span>](repair-a-failed-sql-server-installation.md)  
  
  
