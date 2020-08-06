---
title: Criar um banco de dados do Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 8373bb35-f0f9-4c3c-a53c-dfaa2ce567ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ee90ac5d02489da3b411b12389e949ff3136287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570722"
---
# <a name="create-a-master-data-services-database"></a><span data-ttu-id="bc7e8-102">Criar um banco de dados do Master Data Services</span><span class="sxs-lookup"><span data-stu-id="bc7e8-102">Create a Master Data Services Database</span></span>
  <span data-ttu-id="bc7e8-103">Crie um banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] quando precisar de um novo banco de dados para oferecer suporte ao aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] e ao serviço Web do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc7e8-103">Create a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database when you need a new database to support the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bc7e8-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bc7e8-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="bc7e8-105">Para obter informações sobre os requisitos para o computador que hospeda o banco de dados, veja [Requisitos do banco de dados &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bc7e8-105">For information about the requirements for the computer that hosts the database, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
### <a name="to-create-a-master-data-services-database"></a><span data-ttu-id="bc7e8-106">Para criar um banco de dados do Master Data Services</span><span class="sxs-lookup"><span data-stu-id="bc7e8-106">To create a Master Data Services database</span></span>  
  
1.  <span data-ttu-id="bc7e8-107">Abra o [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc7e8-107">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="bc7e8-108">No painel esquerdo, clique em **Configuração do Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="bc7e8-108">In the left pane, click **Database Configuration**.</span></span>  
  
3.  <span data-ttu-id="bc7e8-109">Na página **Configuração do Banco de Dados** , clique em **Criar Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="bc7e8-109">On the **Database Configuration** page, click **Create Database**.</span></span>  
  
4.  <span data-ttu-id="bc7e8-110">Conclua o assistente **Criar Banco de Dados** para criar e configurar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc7e8-110">Complete the **Create Database** wizard to create and configure the database.</span></span> <span data-ttu-id="bc7e8-111">Para obter informações sobre as opções da interface do usuário no assistente, veja [Assistente para Criar Banco de Dados &#40;Master Data Services Configuration Manager&#41;](../create-database-wizard-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="bc7e8-111">For information about the user interface (UI) options in the wizard, see [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bc7e8-112">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bc7e8-112">Next Steps</span></span>  
  
-   <span data-ttu-id="bc7e8-113">Defina as configurações do sistema para o banco de dados e o aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="bc7e8-113">Configure system settings for the database and web application.</span></span> <span data-ttu-id="bc7e8-114">Para obter mais informações, veja [Configurações do sistema &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bc7e8-114">For more information, see [System Settings &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="bc7e8-115">Crie um aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] para associar a este banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc7e8-115">Create a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to associate with this database.</span></span> <span data-ttu-id="bc7e8-116">Para obter mais informações, veja [Criar um aplicativo Web do Master Data Manager &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bc7e8-116">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="bc7e8-117">Configure um plano de manutenção para fazer backup dos logs de banco de dados e de transação.</span><span class="sxs-lookup"><span data-stu-id="bc7e8-117">Configure a maintenance plan to back up the database and transaction logs.</span></span> <span data-ttu-id="bc7e8-118">Para obter mais informações, veja [Requisitos do banco de dados &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bc7e8-118">For more information, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc7e8-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc7e8-119">See Also</span></span>  
 [<span data-ttu-id="bc7e8-120">Instalar o Master Data Services</span><span class="sxs-lookup"><span data-stu-id="bc7e8-120">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
