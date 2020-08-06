---
title: Criar um aplicativo Web do Master Data Manager (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 241d46d7-8008-47f6-bebd-0dfff1cc856a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fd81188b499850397aa8ffd2e40cfcb91c648288
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570723"
---
# <a name="create-a-master-data-manager-web-application-master-data-services"></a><span data-ttu-id="4eb2f-102">Criar um aplicativo Web do Master Data Manager (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4eb2f-102">Create a Master Data Manager Web Application (Master Data Services)</span></span>
  <span data-ttu-id="4eb2f-103">O aplicativo Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] oferece uma interface para usuários trabalharem com dados mestre e para administradores configurarem e administrarem o MDS.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application provides an interface for users to work with master data and for administrators to configure and administer MDS.</span></span>  
  
 <span data-ttu-id="4eb2f-104">Um aplicativo Web sempre deve ser contido por um site.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-104">A web application must always be contained by a website.</span></span> <span data-ttu-id="4eb2f-105">Para criar um aplicativo Web, você deve:</span><span class="sxs-lookup"><span data-stu-id="4eb2f-105">To create a web application, you must either:</span></span>  
  
-   <span data-ttu-id="4eb2f-106">Usar o site Padrão e criar o aplicativo Web,</span><span class="sxs-lookup"><span data-stu-id="4eb2f-106">Use the Default website and then create the web application,</span></span>  
  
-   <span data-ttu-id="4eb2f-107">Usar um site existente e criar o aplicativo Web ou</span><span class="sxs-lookup"><span data-stu-id="4eb2f-107">Use an existing website and then create the web application, or</span></span>  
  
-   <span data-ttu-id="4eb2f-108">Criar um novo site, que cria automaticamente um aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-108">Create a new website, which automatically creates a web application.</span></span>  
  
 <span data-ttu-id="4eb2f-109">Após criar o aplicativo Web, associe-o com o banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eb2f-109">After you create the web application, you associate it with the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4eb2f-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4eb2f-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="4eb2f-111">Para obter informações sobre os requisitos para o computador que hospeda o aplicativo Web, consulte [Requisitos do aplicativo Web &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4eb2f-111">For information about the requirements for the computer that hosts the web application, see [Web Application Requirements &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="4eb2f-112">Para criar um aplicativo Web do Master Data Manager em um novo site</span><span class="sxs-lookup"><span data-stu-id="4eb2f-112">To create a Master Data Manager web application in a new website</span></span>  
 <span data-ttu-id="4eb2f-113">Quando você cria um novo site, o aplicativo Web raiz é o aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eb2f-113">When you create a new website, the root web application is the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="4eb2f-114">O aplicativo Web também é adicionado a um novo pool de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-114">The web application is also added to a new application pool.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4eb2f-115">Se você seguir este procedimento, não poderá especificar um caminho virtual e um alias do aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eb2f-115">If you follow this procedure, you cannot specify a virtual path and alias of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="4eb2f-116">Se desejar especificar um caminho virtual e um alias para o [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], crie um aplicativo Web em um site existente que ainda não esteja configurado como um aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eb2f-116">If you want to specify a virtual path and alias for [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must create a web application in an existing website that is not already configured as a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="4eb2f-117">Adicionalmente, o [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] só oferece suporte à criação de sites com associações de HTTP.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-117">Additionally, [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] supports creating sites with HTTP bindings only.</span></span> <span data-ttu-id="4eb2f-118">Para adicionar uma associação de HTTPS, crie um novo site e aplicativo no [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] e, em seguida, consulte [Proteger um aplicativo Web Master Data Manager](secure-a-master-data-manager-web-application.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-118">To add an HTTPS binding, create a new site and application in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] and then see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md) for more information.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="4eb2f-119">Para criar um aplicativo Web do Master Data Manager em um novo site</span><span class="sxs-lookup"><span data-stu-id="4eb2f-119">To create a Master Data Manager web application in a new website</span></span>  
  
1.  <span data-ttu-id="4eb2f-120">Abra o [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4eb2f-120">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="4eb2f-121">No painel esquerdo, clique em **Configuração da Web**.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-121">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="4eb2f-122">Na página **Configuração da Web** , na lista de Sites, selecione **Criar novo site**.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-122">On the **Web Configuration** page, in the Website list, select **Create new website**.</span></span>  
  
4.  <span data-ttu-id="4eb2f-123">Na caixa de diálogo **Criar Site** , especifique as informações para um novo site.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-123">On the **Create Website** dialog box, specify information for a new website.</span></span> <span data-ttu-id="4eb2f-124">Para obter mais informações sobre as opções da interface do usuário na caixa de diálogo, consulte [Caixa de diálogo Criar Site &#40;Gerenciador de Configuração do Master Data Services&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4eb2f-124">For more information about the user interface (UI) options in the dialog box, see [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="4eb2f-125">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-125">Click **OK**.</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="4eb2f-126">Para criar um aplicativo Web do Master Data Manager em um site existente</span><span class="sxs-lookup"><span data-stu-id="4eb2f-126">To create a Master Data Manager web application in an existing website</span></span>  
 <span data-ttu-id="4eb2f-127">Ao criar um aplicativo Web em um site existente, você pode escolher o caminho virtual e o alias do aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-127">When you create a web application in an existing website, you can choose the virtual path and alias of the web application.</span></span> <span data-ttu-id="4eb2f-128">O aplicativo Web é adicionado a um novo pool de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-128">The web application is added to a new application pool.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="4eb2f-129">Para criar um aplicativo Web do Master Data Manager em um site existente</span><span class="sxs-lookup"><span data-stu-id="4eb2f-129">To create a Master Data Manager web application in an existing website</span></span>  
  
1.  <span data-ttu-id="4eb2f-130">Abra o [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4eb2f-130">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="4eb2f-131">No painel esquerdo, clique em **Configuração da Web**.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-131">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="4eb2f-132">Na página **Configuração da Web** , da lista **Site** , selecione o site no qual você deseja criar o aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eb2f-132">On the **Web Configuration** page, from the **Website** list, select the website in which you want to create the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="4eb2f-133">Clique em **Criar Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-133">Click **Create Application**.</span></span>  
  
5.  <span data-ttu-id="4eb2f-134">Na caixa de diálogo **Criar Aplicativo Web** , especifique as informações para um novo aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-134">On the **Create Web Application** dialog box, specify information for a new web application.</span></span> <span data-ttu-id="4eb2f-135">Para obter mais informações sobre as opções da interface do usuário na caixa de diálogo, consulte [Caixa de diálogo Criar Aplicativo Web &#40;Gerenciador de Configuração do Master Data Services&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4eb2f-135">For more information about the user interface (UI) options in the dialog box, see [Create Web Application Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
6.  <span data-ttu-id="4eb2f-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-136">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4eb2f-137">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4eb2f-137">Next Steps</span></span>  
  
-   <span data-ttu-id="4eb2f-138">Associe o aplicativo Web a um banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eb2f-138">Associate the web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="4eb2f-139">Para obter mais informações, consulte [Associar um banco de dados do Master Data Services a um aplicativo Web](associate-a-master-data-services-database-and-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="4eb2f-139">For more information, see [Associate a Master Data Services Database and Web Application](associate-a-master-data-services-database-and-web-application.md).</span></span>  
  
-   <span data-ttu-id="4eb2f-140">Opcionalmente, configure o site que hospeda o aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] para usar uma associação de HTTPS se quiser criptografar o conteúdo usando o protocolo SSL.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-140">Optionally, configure the website that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to use an HTTPS binding if you want to encrypt content by using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="4eb2f-141">Você deverá usar uma ferramenta do IIS (Serviço de Informações da Internet), como o Gerenciador do IIS, para configurar o certificado do servidor para o servidor Web e para configurar uma associação de HTTPS e as configurações de SSL do site.</span><span class="sxs-lookup"><span data-stu-id="4eb2f-141">You must use an Internet Information Services (IIS) tool, such as IIS Manager, to configure the server certificate for the web server, and to configure an HTTPS binding and the SSL settings for the site.</span></span> <span data-ttu-id="4eb2f-142">Para obter mais informações, consulte [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="4eb2f-142">For more information, see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eb2f-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4eb2f-143">See Also</span></span>  
 [<span data-ttu-id="4eb2f-144">Instalar o Master Data Services</span><span class="sxs-lookup"><span data-stu-id="4eb2f-144">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
