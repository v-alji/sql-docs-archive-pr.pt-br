---
title: Conceder permissões para Integration Services serviço | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c2caa68-7834-4ea0-bd77-4f3a7c86d634
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e7ab0c2f482e5a0b1bfeaa06f38ec5a886420a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570137"
---
# <a name="grant-permissions-to-integration-services-service"></a><span data-ttu-id="698f1-102">Conceder permissões ao serviço Integration Services</span><span class="sxs-lookup"><span data-stu-id="698f1-102">Grant Permissions to Integration Services Service</span></span>
  <span data-ttu-id="698f1-103">Nas versões anteriores do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], por padrão, quando você instalava o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , todos os usuários no grupo Usuários tinham acesso ao serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="698f1-103">In previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], by default when you installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] all users in the Users group had access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="698f1-104">Quando você instala a versão atual do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], os usuários não têm acesso ao serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="698f1-104">When you install the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], users do not have access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="698f1-105">Por padrão, o serviço é protegido.</span><span class="sxs-lookup"><span data-stu-id="698f1-105">The service is secure by default.</span></span> <span data-ttu-id="698f1-106">Depois que o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] é instalado, o administrador deve conceder acesso ao serviço.</span><span class="sxs-lookup"><span data-stu-id="698f1-106">After [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is installed, the administrator must grant access to the service.</span></span>  
  
### <a name="to-grant-access-to-the-integration-services-service"></a><span data-ttu-id="698f1-107">Para conceder acesso ao serviço Integration Services</span><span class="sxs-lookup"><span data-stu-id="698f1-107">To grant access to the Integration Services service</span></span>  
  
1.  <span data-ttu-id="698f1-108">Execute Dcomcnfg.exe.</span><span class="sxs-lookup"><span data-stu-id="698f1-108">Run Dcomcnfg.exe.</span></span> <span data-ttu-id="698f1-109">Dcomcnfg.exe fornece uma interface do usuário para modificar certas configurações no Registro.</span><span class="sxs-lookup"><span data-stu-id="698f1-109">Dcomcnfg.exe provides a user interface for modifying certain settings in the registry.</span></span>  
  
2.  <span data-ttu-id="698f1-110">Na caixa de diálogo **Serviços de Componentes**, expanda o nó Serviços de Componentes > Computadores > Meu Computador > Configuração de DCOM.</span><span class="sxs-lookup"><span data-stu-id="698f1-110">In the **Component Services** dialog, expand the Component Services > Computers > My Computer > DCOM Config node.</span></span>  
  
3.  <span data-ttu-id="698f1-111">Clique com o botão direito do mouse em **Microsoft SQL Server Integration Services 12,0**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="698f1-111">Right-click **Microsoft SQL Server Integration Services 12.0**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="698f1-112">Na guia **Segurança** , clique em **Editar** na área **Permissões de Inicialização e Ativação** .</span><span class="sxs-lookup"><span data-stu-id="698f1-112">On the **Security** tab, click **Edit** in the **Launch and Activation Permissions** area.</span></span>  
  
5.  <span data-ttu-id="698f1-113">Adicione os usuários e atribua permissões apropriadas e clique em Ok.</span><span class="sxs-lookup"><span data-stu-id="698f1-113">Add users and assign appropriate permissions, and then click Ok.</span></span>  
  
6.  <span data-ttu-id="698f1-114">Repita as etapas 4 a 5 para Permissões de Acesso.</span><span class="sxs-lookup"><span data-stu-id="698f1-114">Repeat steps 4 - 5 for Access Permissions.</span></span>  
  
7.  <span data-ttu-id="698f1-115">Reinicie o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="698f1-115">Restart SQL Server Management Studio.</span></span>  
  
8.  <span data-ttu-id="698f1-116">Reinicie o serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="698f1-116">Restart the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Service.</span></span>  
  
  
