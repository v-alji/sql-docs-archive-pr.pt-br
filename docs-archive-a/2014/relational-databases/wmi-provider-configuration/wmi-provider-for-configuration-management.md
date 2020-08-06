---
title: Provedor WMI para conceitos de gerenciamento de configuração | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- WMI Provider for Configuration Management
- SQL Server WMI Provider
- configuration management [WMI]
- WMI Provider for Configuration Management, about WMI Provider for Configuration Management
ms.assetid: 7e41db24-b915-4eb8-a1d6-e6948ee915b7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: be0682e7d6de5cb8c3d67a2f300bb89122213652
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571875"
---
# <a name="wmi-provider-for-configuration-management-concepts"></a><span data-ttu-id="f6093-102">Provedor WMI para conceitos de gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="f6093-102">WMI Provider for Configuration Management Concepts</span></span>
  <span data-ttu-id="f6093-103">O provedor WMI é uma camada publicada que é usada com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] snap-in Configuration Manager para [!INCLUDE[msCoName](../../includes/msconame-md.md)] o console de gerenciamento (MMC) e o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6093-103">The WMI provider is a published layer that is used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager snap-in for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (MMC) and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="f6093-104">Ele fornece uma forma unificada para fazer a interface com chamadas de API que gerenciam as operações do Registro solicitadas pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager e fornece controle e manipulação aprimorados sobre os serviços selecionados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6093-104">It provides a unified way for interfacing with the API calls that manage the registry operations requested by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and provides enhanced control and manipulation over the selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services.</span></span>  
  
 <span data-ttu-id="f6093-105">O Provedor WMI do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é uma DLL e um arquivo MOF, que são compilados automaticamente pela Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6093-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider is a DLL and a MOF file, which are compiled automatically by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
 <span data-ttu-id="f6093-106">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor WMI contém um conjunto de classes de objeto usado para controlar os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] serviços usando os seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="f6093-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider contains a set of object classes used to control the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services using the following methods:</span></span>  
  
-   <span data-ttu-id="f6093-107">Uma linguagem de script, como VBScript, [!INCLUDE[jsprjscript](../../includes/jsprjscript-md.md)] ou Perl, nos quais é possível inserir o WQL (Windows Query Language).</span><span class="sxs-lookup"><span data-stu-id="f6093-107">A script language such as VBScript, [!INCLUDE[jsprjscript](../../includes/jsprjscript-md.md)], or Perl, in which Windows Query Language (WQL) can be embedded.</span></span>  
  
-   <span data-ttu-id="f6093-108">O OBJETO <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> em um programa de código gerenciado SMO.</span><span class="sxs-lookup"><span data-stu-id="f6093-108">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object in an SMO managed code program.</span></span>  
  
-   <span data-ttu-id="f6093-109">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager ou MMC com o snap-in do provedor WMI do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6093-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or MMC with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI provider snap-in.</span></span>  
  
## <a name="using-a-script-language"></a><span data-ttu-id="f6093-110">Usando uma linguagem de script</span><span class="sxs-lookup"><span data-stu-id="f6093-110">Using a Script Language</span></span>  
 <span data-ttu-id="f6093-111">As vantagens de usar uma linguagem de script incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f6093-111">The advantages of using a script language include the following:</span></span>  
  
-   <span data-ttu-id="f6093-112">Um ambiente de desenvolvimento não é necessário.</span><span class="sxs-lookup"><span data-stu-id="f6093-112">A development environment is not required.</span></span>  
  
-   <span data-ttu-id="f6093-113">Os arquivos que dão suporte à linguagem de script estão amplamente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f6093-113">The files that support the script language are widely available.</span></span>  
  
 <span data-ttu-id="f6093-114">O script também pode funcionar com outros Provedores WMI, além do Provedor WMI do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6093-114">The script can also work with other WMI Providers in addition to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] WMI Provider.</span></span> <span data-ttu-id="f6093-115">Um administrador de domínio pode usar um script para configurar os serviços, as configurações de rede e as configurações de alias em vários computadores em uma rede.</span><span class="sxs-lookup"><span data-stu-id="f6093-115">A domain administrator can use a script to set up the services, network settings, and alias settings on multiple computers on a network.</span></span>  
  
 <span data-ttu-id="f6093-116">Esta seção trata mais detalhadamente do acesso ao Provedor WMI para Configuration Manager a partir de scripts.</span><span class="sxs-lookup"><span data-stu-id="f6093-116">This section deals with accessing the WMI Provider for Configuration Management from scripts in further detail.</span></span>  
  
## <a name="using-the-smo-managedcomputer-object"></a><span data-ttu-id="f6093-117">Usando o objeto ManagedComputer do SMO</span><span class="sxs-lookup"><span data-stu-id="f6093-117">Using the SMO ManagedComputer Object</span></span>  
 <span data-ttu-id="f6093-118">O objeto <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> é um objeto gerenciado do SMO que fornece acesso ao Provedor WMI para Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f6093-118">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object is a managed SMO object that provides access to the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="f6093-119">Com um programa SMO, o objeto <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> pode ser usado para exibir e modificar serviços, configurações de rede e configurações de alias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6093-119">By using an SMO program, the <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object can be used to view and modify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network settings, and alias settings.</span></span> <span data-ttu-id="f6093-120">Para obter mais informações, consulte [Gerenciando serviços e configurações de rede usando o provedor WMI](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="f6093-120">For more information, see [Managing Services and Network Settings by Using WMI Provider](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span></span>  
  
## <a name="using-the-microsoft-management-console-or-sql-server-configuration-manager"></a><span data-ttu-id="f6093-121">Usando o Console de Gerenciamento Microsoft ou o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f6093-121">Using the Microsoft Management Console or SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="f6093-122">O MMC fornece uma interface para gerenciar serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], em vez de uma linguagem de script ou um programa de código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f6093-122">Microsoft Management Console (MMC) provides an interface to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, as opposed to a scripting language or managed code program.</span></span> <span data-ttu-id="f6093-123">O snap-in do MMC de gerenciamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode ser usado para interromper e iniciar serviços, e para alterar contas de serviço.</span><span class="sxs-lookup"><span data-stu-id="f6093-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management MMC snap-in can be used to stop and start services, and to change service accounts.</span></span>  
  
 <span data-ttu-id="f6093-124">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager também pode ser usado para gerenciar serviços, protocolos de cliente e de servidor e aliases de servidor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6093-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager can also be used to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, client and server protocols, and server aliases</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6093-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6093-125">See Also</span></span>  
 <span data-ttu-id="f6093-126">[Noções básicas sobre o provedor WMI para gerenciamento de configuração](understanding-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="f6093-126">[Understanding the WMI Provider for Configuration Management](understanding-the-wmi-provider-for-configuration-management.md) </span></span>  
 <span data-ttu-id="f6093-127">[Trabalhando com o provedor WMI para gerenciamento de configuração](working-with-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="f6093-127">[Working with the WMI Provider for Configuration Management](working-with-the-wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="f6093-128">Usando as linguagens WQL e de scripts com o provedor WMI para gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="f6093-128">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>](using-wql-and-scripting-languages-with-the-wmi-provider.md)  
  
  
