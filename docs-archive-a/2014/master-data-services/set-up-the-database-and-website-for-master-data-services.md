---
title: Configurar o banco de dados e o site para Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
f1_keywords:
- sql12.mds.configmanager.general.f1
ms.assetid: d50863e7-50d9-4ab8-aabb-fd68e2d132a1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da797bc6f9838a2baab6cc440cc7d778a7a6e186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583696"
---
# <a name="set-up-the-database-and-website-for-master-data-services"></a><span data-ttu-id="3ad4d-102">Instalar o banco de dados e o site para o Master Data Services</span><span class="sxs-lookup"><span data-stu-id="3ad4d-102">Set up the Database and Website for Master Data Services</span></span>
  <span data-ttu-id="3ad4d-103">Use o [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] para instalar o banco de dados e o site do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span><span class="sxs-lookup"><span data-stu-id="3ad4d-103">Use the [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to set up the database and website for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span></span>  
  
 <span data-ttu-id="3ad4d-104">Para instalar o banco de dados e o site, conclua as seguintes tarefas.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-104">To set up the database and website, complete the following tasks.</span></span>  
  
1.  <span data-ttu-id="3ad4d-105">Crie um banco de dados usando a página **configuração de banco de dados** no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ad4d-105">Create a database using the **Database Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="3ad4d-106">Para obter informações, consulte [página de configuração de banco de dados &#40;Gerenciador de Configuração do Master Data Services&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) e [Assistente para criar banco de dados &#40;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md)Gerenciador de configuração do Master Data Services&#41;.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-106">For information, see [Database Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) and [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
2.  <span data-ttu-id="3ad4d-107">Crie um novo site, selecione o site padrão ou selecione outro site existente, usando a página **configuração da Web** no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ad4d-107">Create a new website, select the default website, or select another existing website, using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="3ad4d-108">Em seguida, associe o banco de dados do MDS ao aplicativo Web que você selecionar ou criar.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-108">Then associate the MDS database with the web application you select or create.</span></span>  
  
     <span data-ttu-id="3ad4d-109">Para obter informações, consulte a [página configuração da Web &#40;Gerenciador de Configuração do Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) e a [caixa de diálogo criar site &#40;Gerenciador de configuração do Master Data Services ](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md)&#41;.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-109">For information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
3.  <span data-ttu-id="3ad4d-110">Adicional Habilite a integração com o Data Quality Services usando a página **configuração da Web** no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ad4d-110">(Optional) Enable integration with Data Quality Services using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="3ad4d-111">Para obter mais informações, consulte a [página de configuração da Web &#40;Gerenciador de Configuração do Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) e [habilitar a integração do Data Quality Services com o Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3ad4d-111">For more information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Enable Data Quality Services Integration with Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span></span>  
  
 <span data-ttu-id="3ad4d-112">Você também pode usar [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] para especificar configurações para os aplicativos Web e serviços associados ao banco de dados do MDS.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-112">You can also use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to specify settings for the web applications and services associated with the MDS database.</span></span> <span data-ttu-id="3ad4d-113">Por exemplo, você pode especificar a frequência com que os dados são carregados ou os emails de validação são enviados.</span><span class="sxs-lookup"><span data-stu-id="3ad4d-113">For example, you can specify how frequently data is loaded or how often validation emails are sent.</span></span> <span data-ttu-id="3ad4d-114">Para obter mais informações, veja [Configurações do sistema &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3ad4d-114">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ad4d-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ad4d-115">See Also</span></span>  
 <span data-ttu-id="3ad4d-116">[Banco de dados Master Data Services](../../2014/master-data-services/master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="3ad4d-116">[Master Data Services Database](../../2014/master-data-services/master-data-services-database.md) </span></span>  
 [<span data-ttu-id="3ad4d-117">Aplicativo Web Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="3ad4d-117">Master Data Manager Web Application</span></span>](../../2014/master-data-services/master-data-manager-web-application.md)  
  
  
