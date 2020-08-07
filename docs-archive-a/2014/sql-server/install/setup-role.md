---
title: Função de instalação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c7e9db15-89f2-4d4d-8860-1e64c5821c4d
author: heidisteen
ms.author: heidist
ms.openlocfilehash: add000eed671303c78ab0500303f826bafe4ab77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573455"
---
# <a name="setup-role"></a><span data-ttu-id="5ea9c-102">Função de instalação</span><span class="sxs-lookup"><span data-stu-id="5ea9c-102">Setup Role</span></span>
  <span data-ttu-id="5ea9c-103">Use esta página para especificar se deseja usar a página de Seleção de Recursos para selecionar recursos individuais ou se deseja instalar usando uma função de instalação.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-103">Use this page to specify whether to use the Feature Selection page to select individual features, or to install using a setup role.</span></span>  
  
 <span data-ttu-id="5ea9c-104">Uma `setup role` é uma seleção fixa de todos os recursos e componentes compartilhados que são necessários para implementar uma configuração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] predefinida.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-104">A `setup role` is a fixed selection of all the features and shared components that are required to implement a predefined [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] configuration.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ea9c-105">Opções</span><span class="sxs-lookup"><span data-stu-id="5ea9c-105">Options</span></span>  
 <span data-ttu-id="5ea9c-106">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Instalação de recurso**</span><span class="sxs-lookup"><span data-stu-id="5ea9c-106">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Feature Installation**</span></span>  
 <span data-ttu-id="5ea9c-107">Escolha esta opção para selecionar recursos individuais e componentes compartilhados.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-107">Choose this option to select individual features and shared components.</span></span> <span data-ttu-id="5ea9c-108">Os recursos de instância incluem os Serviços de Mecanismo de Banco de Dados, o Analysis Services (modo nativo) e o Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-108">Instance features include Database Engine Services, Analysis Services (native mode), and Reporting Services.</span></span>  
  
 <span data-ttu-id="5ea9c-109">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]PowerPivot para SharePoint**</span><span class="sxs-lookup"><span data-stu-id="5ea9c-109">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerPivot for SharePoint**</span></span>  
 <span data-ttu-id="5ea9c-110">Escolha esta opção para instalar componentes do servidor do Analysis Services em um farm do SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-110">Choose this option to install Analysis Services server components in a SharePoint 2010 farm.</span></span> <span data-ttu-id="5ea9c-111">Esta opção implanta o Serviço de Sistema do PowerPivot e o servidor do Analysis Server em um farm, habilitando o processamento de consultas e dados para pastas de trabalho do Excel publicadas que contenham dados do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] inseridos.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-111">This option deploys the PowerPivot System Service and the Analysis Services server in a farm, enabling query and data processing for published Excel workbooks that contain embedded [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data.</span></span>  
  
 <span data-ttu-id="5ea9c-112">Opcionalmente, você poderá adicionar uma instância do mecanismo de banco de dados relacional à sua instalação se precisar hospedar bancos de dados em um farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-112">Optionally, you can add a relational database engine instance to your installation if you require it to host databases in a SharePoint farm.</span></span> <span data-ttu-id="5ea9c-113">Se o farm já estiver configurado, essa opção poderá ser ignorada.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-113">If the farm is already configured, you can skip this option.</span></span>  
  
 <span data-ttu-id="5ea9c-114">Depois que a Instalação é concluída, você deve configurar o software usando uma das seguintes abordagens: Ferramenta de Configuração do PowerPivot, cmdlets PowerShell ou Administração Central do SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-114">After Setup is finished, you must configure the software using one of the following approaches: PowerPivot Configuration tool, PowerShell cmdlets, or SharePoint 2010 Central Administration.</span></span> <span data-ttu-id="5ea9c-115">Ao contrário do que acontecia nas versões anteriores, a Instalação não executa mais nenhuma tarefa de configuração para uma instalação do PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-115">In contrast with previous releases, Setup no longer performs any configuration tasks for a PowerPivot installation.</span></span>  
  
 <span data-ttu-id="5ea9c-116">Uma instalação baseada em função não inclui o aplicativo cliente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerPivot para Excel.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-116">A role-based installation does not include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerPivot for Excel client application.</span></span> <span data-ttu-id="5ea9c-117">O aplicativo cliente é instalado separadamente.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-117">The client application is installed separately.</span></span>  
  
 <span data-ttu-id="5ea9c-118">**Todos os Recursos com Padrões**</span><span class="sxs-lookup"><span data-stu-id="5ea9c-118">**All Features With Defaults**</span></span>  
 <span data-ttu-id="5ea9c-119">Escolha esta função de instalação para instalar todos os recursos que estão disponíveis para esta versão.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-119">Choose this setup role to install all features that are available for this release.</span></span> <span data-ttu-id="5ea9c-120">Observe que o PowerPivot para SharePoint está excluído dessa função.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-120">Note that PowerPivot for SharePoint is excluded from this role.</span></span> <span data-ttu-id="5ea9c-121">Você deve usar a função de instalação do PowerPivot para SharePoint para instalar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-121">You must use the PowerPivot for SharePoint setup role to install that feature.</span></span>  
  
 <span data-ttu-id="5ea9c-122">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] é configurado para iniciar usando a conta **NT AUTHORITY\NETWORK SERVICE**.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-122">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] is configured to start using the **NT AUTHORITY\NETWORK SERVICE** account.</span></span> <span data-ttu-id="5ea9c-123">O usuário atual será provisionado como membro da função **sysadmin** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ea9c-123">The current user will be provisioned as a member of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**sysadmin** role.</span></span> <span data-ttu-id="5ea9c-124">Os valores definidos por esta opção podem ser substituídos especificando-se parâmetros de linha de comando adicionais.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-124">Values set by this option can be overridden by specifying additional command line parameters.</span></span>  
  
 <span data-ttu-id="5ea9c-125">Quando o sistema operacional não for um controlador de domínio, por padrão o Mecanismo de Banco de Dados e o Reporting Services usarão a conta NTAUTHORITY\NETWORK SERVICE, o Integration Services usará a conta NTAUTHORITY\NETWORK SERVICE e o Iniciador do Daemon de Filtro de Texto Completo do SQL usará a conta NTAUTHORITY\LOCAL SERVICE.</span><span class="sxs-lookup"><span data-stu-id="5ea9c-125">When the operating system is not a domain controller, by default the Database Engine and Reporting Services will use the NTAUTHORITY\NETWORK SERVICE account, Integration Services will use the NTAUTHORITY\NETWORK SERVICE account, and the SQL Full text Filter Daemon Launcher will use the NTAUTHORITY\LOCAL SERVICE account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea9c-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5ea9c-126">See Also</span></span>  
 <span data-ttu-id="5ea9c-127">[Instalando o PowerPivot para SharePoint](https://go.microsoft.com/fwlink/?LinkId=206906) </span><span class="sxs-lookup"><span data-stu-id="5ea9c-127">[Installing PowerPivot for SharePoint](https://go.microsoft.com/fwlink/?LinkId=206906) </span></span>  
 <span data-ttu-id="5ea9c-128">[Requisitos de hardware e software (PowerPivot para SharePoint](https://go.microsoft.com/fwlink/?LinkId=216823) </span><span class="sxs-lookup"><span data-stu-id="5ea9c-128">[Hardware and Software Requirements (PowerPivot for SharePoint](https://go.microsoft.com/fwlink/?LinkId=216823) </span></span>  
 [<span data-ttu-id="5ea9c-129">Seleção de recursos</span><span class="sxs-lookup"><span data-stu-id="5ea9c-129">Feature Selection</span></span>](../../../2014/sql-server/install/feature-selection.md)  
  
  
