---
title: Sobre o Mecanismo de Banco de Dados de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], installing
ms.assetid: d0876e7f-aa52-4dd7-bd5c-029e2ffded5f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 93e3d7a749fe6be47cc84d43509a6f378476b2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681068"
---
# <a name="about-the-sql-server-database-engine"></a><span data-ttu-id="3fec5-102">Sobre o Mecanismo de Banco de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3fec5-102">About the SQL Server Database Engine</span></span>
  <span data-ttu-id="3fec5-103">O componente [!INCLUDE[ssDE](../../includes/ssde-md.md)] do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é o principal serviço para armazenamento, processamento e proteção de dados.</span><span class="sxs-lookup"><span data-stu-id="3fec5-103">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="3fec5-104">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] fornece acesso controlado e processamento rápido de transações para atender aos requisitos dos mais exigentes aplicativos de consumo de dados em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="3fec5-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications in your enterprise.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3fec5-105">dá suporte a até 50 instâncias do [!INCLUDE[ssDE](../../includes/ssde-md.md)] em um único computador.</span><span class="sxs-lookup"><span data-stu-id="3fec5-105">supports up to 50 instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a single computer.</span></span> <span data-ttu-id="3fec5-106">Para criar uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalação típica, consulte [instalar SQL Server 2014 no assistente de instalação &#40;&#41;de ](install-sql-server-from-the-installation-wizard-setup.md)instalação.</span><span class="sxs-lookup"><span data-stu-id="3fec5-106">To create a typical [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
 <span data-ttu-id="3fec5-107">**Importante** Para instalações locais, é necessário executar a Instalação como um administrador.</span><span class="sxs-lookup"><span data-stu-id="3fec5-107">**Important** For local installations, you must run Setup as an administrator.</span></span> <span data-ttu-id="3fec5-108">Se você instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de um compartilhamento remoto, deverá usar uma conta de domínio que tenha permissões de leitura e de execução no compartilhamento remoto.</span><span class="sxs-lookup"><span data-stu-id="3fec5-108">If you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a remote share, you must use a domain account that has read and execute permissions on the remote share.</span></span>  
  
 <span data-ttu-id="3fec5-109">Os seguintes recursos são instalados quando você seleciona o **Mecanismo de Banco de Dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** na página Componentes a Serem Instalados do Assistente de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3fec5-109">The following features are installed when you select **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine** on the Components to Install page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   <span data-ttu-id="3fec5-110">Replicação - é um componente opcional</span><span class="sxs-lookup"><span data-stu-id="3fec5-110">Replication - is an optional component</span></span>  
  
-   <span data-ttu-id="3fec5-111">Pesquisa de Texto Completo - é um componente opcional</span><span class="sxs-lookup"><span data-stu-id="3fec5-111">Full-Text Search - is an optional component</span></span>  
  
-   <span data-ttu-id="3fec5-112">Data Quality Services – é um componente opcional</span><span class="sxs-lookup"><span data-stu-id="3fec5-112">Data Quality Services - is an optional component</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3fec5-113">Nesta versão, se você marcar a caixa de seleção **Data Quality Services** na instalação, o servidor DQS (Data Quality Services) não será instalado.</span><span class="sxs-lookup"><span data-stu-id="3fec5-113">In this release, selecting the **Data Quality Services** check box in setup does not install the Data Quality Services (DQS) server.</span></span> <span data-ttu-id="3fec5-114">Será necessário executar etapas adicionais pós-instalação para instalar o servidor DQS.</span><span class="sxs-lookup"><span data-stu-id="3fec5-114">You will have to perform additional steps post installation to install DQS server.</span></span> <span data-ttu-id="3fec5-115">Para obter mais informações, consulte [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="3fec5-115">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
 <span data-ttu-id="3fec5-116">Os seguintes recursos adicionais são opções para muitos cenários de usuário típicos:</span><span class="sxs-lookup"><span data-stu-id="3fec5-116">The following additional features are options for many typical user scenarios:</span></span>  
  
-   <span data-ttu-id="3fec5-117">Cliente Data Quality</span><span class="sxs-lookup"><span data-stu-id="3fec5-117">Data Quality Client</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   <span data-ttu-id="3fec5-118">Componentes de conectividade</span><span class="sxs-lookup"><span data-stu-id="3fec5-118">Connectivity components</span></span>  
  
-   <span data-ttu-id="3fec5-119">Modelos de programação</span><span class="sxs-lookup"><span data-stu-id="3fec5-119">Programming models</span></span>  
  
-   <span data-ttu-id="3fec5-120">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="3fec5-120">Management tools</span></span>  
  
-   [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]  
  
-   <span data-ttu-id="3fec5-121">Componentes de documentação</span><span class="sxs-lookup"><span data-stu-id="3fec5-121">Documentation components</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fec5-122">Por padrão, os bancos de dados de exemplo e o código de exemplo não são instalados como parte da instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3fec5-122">By default, sample databases and sample code are not installed as part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="3fec5-123">Para instalar bancos de dados e código de exemplo, veja o [site CodePlex](https://go.microsoft.com/fwlink/?LinkId=87843).</span><span class="sxs-lookup"><span data-stu-id="3fec5-123">To install sample databases and sample code, see the [CodePlex Web site](https://go.microsoft.com/fwlink/?LinkId=87843).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fec5-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3fec5-124">See Also</span></span>  
 <span data-ttu-id="3fec5-125">[Recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="3fec5-125">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="3fec5-126">[Edições e componentes do SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="3fec5-126">[Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span></span>  
 <span data-ttu-id="3fec5-127">[Planejando uma instalação do SQL Server](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="3fec5-127">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="3fec5-128">[Soluções de alta disponibilidade &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3fec5-128">[High Availability Solutions &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span></span>  
 [<span data-ttu-id="3fec5-129">Atualize para o SQL Server 2014 usando o assistente de instalação &#40;a instalação&#41;</span><span class="sxs-lookup"><span data-stu-id="3fec5-129">Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;</span></span>](upgrade-sql-server-using-the-installation-wizard-setup.md)  
  
  
