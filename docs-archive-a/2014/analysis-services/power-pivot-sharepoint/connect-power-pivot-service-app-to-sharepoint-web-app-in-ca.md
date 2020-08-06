---
title: Conectar um aplicativo de serviço PowerPivot a um aplicativo Web do SharePoint na administração central | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5da8e29-7ffd-44e7-bf61-344fa5bea8ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5fc6dcde4cc2d18c3650adbab0ec71ef5c6265cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581533"
---
# <a name="connect-a-powerpivot-service-application-to-a-sharepoint-web-application-in-central-administration"></a><span data-ttu-id="27eca-102">Conectar um aplicativo de serviço PowerPivot a um aplicativo Web do SharePoint na Administração Central</span><span class="sxs-lookup"><span data-stu-id="27eca-102">Connect a PowerPivot Service Application to a SharePoint Web Application in Central Administration</span></span>
  <span data-ttu-id="27eca-103">Um aplicativo de serviço PowerPivot pode ser usado por qualquer número de aplicativos Web do SharePoint no farm.</span><span class="sxs-lookup"><span data-stu-id="27eca-103">A PowerPivot service application can be used by any number of SharePoint Web applications in the farm.</span></span> <span data-ttu-id="27eca-104">Para disponibilizar um aplicativo de serviço PowerPivot, adicione-o a uma lista de associações de serviço.</span><span class="sxs-lookup"><span data-stu-id="27eca-104">To make a PowerPivot service application available, you add it to a service association list.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="27eca-105">Deve haver apenas um aplicativo do serviço PowerPivot no grupo padrão para garantir o funcionamento correto do Painel de Gerenciamento PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="27eca-105">You must have one PowerPivot service application in the default group to ensure that PowerPivot Management Dashboard works properly.</span></span> <span data-ttu-id="27eca-106">Não adicione mais de um aplicativo de serviço PowerPivot ao grupo padrão.</span><span class="sxs-lookup"><span data-stu-id="27eca-106">Do not add more than one PowerPivot service application to the default group.</span></span> <span data-ttu-id="27eca-107">A adição de várias entradas do mesmo tipo de aplicativo do serviço não é uma configuração compatível e pode causar erros.</span><span class="sxs-lookup"><span data-stu-id="27eca-107">Adding multiple entries of the same service application type is not a supported configuration and might cause errors.</span></span> <span data-ttu-id="27eca-108">Se você estiver criando aplicativos de serviço adicionais, adicione-os a listas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="27eca-108">If you are creating additional service applications, add them to custom lists.</span></span>  
  
 <span data-ttu-id="27eca-109">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="27eca-109">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="27eca-110">Adicionar um aplicativo de serviço PowerPivot ao grupo padrão</span><span class="sxs-lookup"><span data-stu-id="27eca-110">Add PowerPivot Services Application to the Default Group</span></span>](#default)  
  
 [<span data-ttu-id="27eca-111">Adicionar um aplicativo de serviço PowerPivot a uma lista de associações de serviço personalizada</span><span class="sxs-lookup"><span data-stu-id="27eca-111">Add PowerPivot Services Application a Custom Service Association List</span></span>](#custom)  
  
##  <a name="add-powerpivot-services-application-to-the-default-group"></a><a name="default"></a><span data-ttu-id="27eca-112">Adicionar aplicativo de serviços PowerPivot ao grupo padrão</span><span class="sxs-lookup"><span data-stu-id="27eca-112">Add PowerPivot Services Application to the Default Group</span></span>  
 <span data-ttu-id="27eca-113">Uma lista de associações de serviço é uma lista de serviços compartilhados que fornece recursos a outros aplicativos Web do SharePoint no farm.</span><span class="sxs-lookup"><span data-stu-id="27eca-113">A service association list is a list of shared services that provide resources to other SharePoint Web applications in the farm.</span></span> <span data-ttu-id="27eca-114">Há um grupo padrão de associações de serviço para o farm.</span><span class="sxs-lookup"><span data-stu-id="27eca-114">There is one default group of service associations for the farm.</span></span>  
  
 <span data-ttu-id="27eca-115">Para constar na lista, um aplicativo de serviço PowerPivot pode ser adicionado quando você cria o aplicativo, ou posteriormente, usando as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="27eca-115">To be on the list, a PowerPivot service application can either be added when you create the application or afterwards by using the following steps.</span></span>  
  
1.  <span data-ttu-id="27eca-116">Na Administração Central, em **Gerenciamento de Aplicativo**, clique em **Configurar associações de aplicativos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="27eca-116">In Central Administration, in **Application Management**, click **Configure service application associations**.</span></span>  
  
2.  <span data-ttu-id="27eca-117">Em Grupo Proxy de Aplicativo, clique em **padrão**.</span><span class="sxs-lookup"><span data-stu-id="27eca-117">In Application Proxy Group, click **default**.</span></span>  
  
3.  <span data-ttu-id="27eca-118">Marque a caixa de seleção ao lado do aplicativo de serviço PowerPivot (indicado pelo nome do tipo `PowerPivot Service Application Proxy`).</span><span class="sxs-lookup"><span data-stu-id="27eca-118">Select the checkbox next to the PowerPivot service application (indicated by type name `PowerPivot Service Application Proxy`).</span></span> <span data-ttu-id="27eca-119">Se houver mais de um aplicativo de serviço PowerPivot, escolha apenas um.</span><span class="sxs-lookup"><span data-stu-id="27eca-119">If you have more than one PowerPivot service application, choose just one.</span></span>  
  
4.  <span data-ttu-id="27eca-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="27eca-120">Click **OK**.</span></span>  
  
##  <a name="add-powerpivot-services-application-a-custom-service-association-list"></a><a name="custom"></a><span data-ttu-id="27eca-121">Adicionar um aplicativo de serviços PowerPivot a uma lista de associação de serviço personalizada</span><span class="sxs-lookup"><span data-stu-id="27eca-121">Add PowerPivot Services Application a Custom Service Association List</span></span>  
 <span data-ttu-id="27eca-122">O grupo padrão pode ser substituído por uma lista personalizada.</span><span class="sxs-lookup"><span data-stu-id="27eca-122">The default group can be replaced by a custom list.</span></span> <span data-ttu-id="27eca-123">Uma lista personalizada é criada especificamente para um único aplicativo Web do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="27eca-123">A custom list is created specifically for a single SharePoint Web application.</span></span> <span data-ttu-id="27eca-124">Ela substitui o grupo padrão e o substitui por apenas uma dessas associações de serviço que um administrador de farm ou serviço especifica.</span><span class="sxs-lookup"><span data-stu-id="27eca-124">It overrides the default group and replaces it with only those service associations that a farm or service administrator specifies.</span></span> <span data-ttu-id="27eca-125">Se você criou vários aplicativos de serviço PowerPivot, deverá usar uma lista personalizada para especificar o que será usado.</span><span class="sxs-lookup"><span data-stu-id="27eca-125">If you created multiple PowerPivot service applications, you must use a custom list to specify which one to use.</span></span> <span data-ttu-id="27eca-126">Uma lista personalizada não pode ser reutilizada por outros aplicativos Web.</span><span class="sxs-lookup"><span data-stu-id="27eca-126">A custom list cannot be reused by other Web applications.</span></span> <span data-ttu-id="27eca-127">Ela só se aplica ao aplicativo Web para o qual foi criada.</span><span class="sxs-lookup"><span data-stu-id="27eca-127">It applies only to the Web application for which it was created.</span></span>  
  
1.  <span data-ttu-id="27eca-128">Na Administração Central, em **Gerenciamento de Aplicativo**, clique em **Gerenciar aplicativos Web**.</span><span class="sxs-lookup"><span data-stu-id="27eca-128">In Central Administration, in **Application Management**, click **Manage web applications**.</span></span>  
  
2.  <span data-ttu-id="27eca-129">Selecione o aplicativo (por exemplo, SharePoint -80).</span><span class="sxs-lookup"><span data-stu-id="27eca-129">Select the application (for example, SharePoint -80).</span></span>  
  
3.  <span data-ttu-id="27eca-130">Em Aplicativos Web, em Gerenciar, clique em **Conexões de Serviço**.</span><span class="sxs-lookup"><span data-stu-id="27eca-130">In Web Applications, in Manage, click **Service Connections**.</span></span>  
  
4.  <span data-ttu-id="27eca-131">Em **Editar o seguinte grupo de conexões**, selecione **[personalizado]**.</span><span class="sxs-lookup"><span data-stu-id="27eca-131">In **Edit the following group of connections**, select **[custom]**.</span></span>  
  
5.  <span data-ttu-id="27eca-132">Marque a caixa de seleção ao lado de cada conexão de aplicativo de serviço a ser usada.</span><span class="sxs-lookup"><span data-stu-id="27eca-132">Select the checkbox next to each service application connection you want to use.</span></span> <span data-ttu-id="27eca-133">Se você tiver vários aplicativos de serviço PowerPivot (indicado por Tipo definido como `PowerPivot Service Application Proxy`), escolha apenas um.</span><span class="sxs-lookup"><span data-stu-id="27eca-133">If you have multiple PowerPivot service applications (indicated by Type set to `PowerPivot Service Application Proxy`), be sure to choose only one.</span></span>  
  
6.  <span data-ttu-id="27eca-134">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="27eca-134">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27eca-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="27eca-135">See Also</span></span>  
 <span data-ttu-id="27eca-136">[Criar e configurar um aplicativo de serviço PowerPivot na administração central](create-and-configure-power-pivot-service-application-in-ca.md) </span><span class="sxs-lookup"><span data-stu-id="27eca-136">[Create and Configure a PowerPivot Service Application in Central Administration](create-and-configure-power-pivot-service-application-in-ca.md) </span></span>  
 [<span data-ttu-id="27eca-137">PowerPivot para SharePoint de configuração inicial &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="27eca-137">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
  
