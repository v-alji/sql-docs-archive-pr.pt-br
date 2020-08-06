---
title: Associar um banco de dados do Master Data Services a um aplicativo Web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ccb25672-f71d-4135-b548-f50eb45d8fa5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 01afde6aea5065a51cb9e7ae5dc4151e9f1e9fc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679391"
---
# <a name="associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="40d10-102">Associar um banco de dados do Master Data Services a um aplicativo Web</span><span class="sxs-lookup"><span data-stu-id="40d10-102">Associate a Master Data Services Database and Web Application</span></span>
  <span data-ttu-id="40d10-103">Associe seu aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] a um banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] para especificar o banco de dados a ser usado em operações da Web.</span><span class="sxs-lookup"><span data-stu-id="40d10-103">Associate your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database to specify the database to use for web operations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="40d10-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="40d10-104">Prerequisites</span></span>  
  
-   [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] <span data-ttu-id="40d10-105">deve estar instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="40d10-105">must be installed on the local computer.</span></span> <span data-ttu-id="40d10-106">Para obter mais informações, confira [Instalar o Master Data Services](install-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="40d10-106">For more information, see [Install Master Data Services](install-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="40d10-107">Deve existir um aplicativo Web local do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40d10-107">A local [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application must exist.</span></span> <span data-ttu-id="40d10-108">Para obter mais informações, veja [Criar um aplicativo Web do Master Data Manager &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="40d10-108">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="40d10-109">Deve existir um banco de dados local ou remoto do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40d10-109">Either a local or remote [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database must exist.</span></span> <span data-ttu-id="40d10-110">Para obter mais informações, veja [Criar um banco de dados do Master Data Services](create-a-master-data-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="40d10-110">For more information, see [Create a Master Data Services Database](create-a-master-data-services-database.md).</span></span>  
  
### <a name="to-associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="40d10-111">Para associar um banco de dados do Master Data Services e um aplicativo Web</span><span class="sxs-lookup"><span data-stu-id="40d10-111">To associate a Master Data Services database and web application</span></span>  
  
1.  <span data-ttu-id="40d10-112">Abra o [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40d10-112">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="40d10-113">No painel esquerdo, clique em **Configuração da Web**.</span><span class="sxs-lookup"><span data-stu-id="40d10-113">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="40d10-114">Na página **Configuração da Web** , em **Aplicativo Web**, na lista **Site** , selecione o site que contém seu aplicativo Web do [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40d10-114">On the **Web Configuration** page, under **Web application**, from the **Website** list, select the website that contains your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="40d10-115">Na caixa **Aplicativo Web** , selecione o aplicativo Web que hospeda o [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40d10-115">In the **Web application** box, select the web application that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
5.  <span data-ttu-id="40d10-116">Em **Aplicativo Associado com Banco de dados**, clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="40d10-116">Under **Associate Application with Database**, click **Select**.</span></span> <span data-ttu-id="40d10-117">A caixa de diálogo **Conectar ao Banco de Dados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="40d10-117">The **Connect to Database** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="40d10-118">Especifique informações de conexão para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda o banco de dados do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="40d10-118">Specify connection information for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database, and click **Connect**.</span></span>  
  
7.  <span data-ttu-id="40d10-119">Na lista **Banco de dados do Master Data Services** , selecione o banco de dados a ser associado ao aplicativo Web e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="40d10-119">From the **Master Data Services database** list, select the database you want to associate the web application with and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="40d10-120">Em **Associar Aplicativo ao Banco de Dados**, verifique se as informações de instância e banco de dados estão corretas e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="40d10-120">Under **Associate Application with Database**, verify that the instance and database information are correct, and then click **Apply**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="40d10-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="40d10-121">Next Steps</span></span>  
  
-   <span data-ttu-id="40d10-122">O acesso programático a serviços Web do [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] é habilitado automaticamente quando o aplicativo Web é criado.</span><span class="sxs-lookup"><span data-stu-id="40d10-122">Programmatic access to [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web services is automatically enabled when the web application is created.</span></span> <span data-ttu-id="40d10-123">Para permitir que desenvolvedores acessem os metadados de serviço para gerar classes de proxy facilmente para o acesso programático, habilite a publicação de metadados.</span><span class="sxs-lookup"><span data-stu-id="40d10-123">To let developers access the service metadata to easily generate proxy classes for programmatic access, enable metadata publishing.</span></span> <span data-ttu-id="40d10-124">Para obter mais informações, veja [Criar classes proxy do serviço Web do Master Data Manager](../develop/create-master-data-manager-web-service-proxy-classes.md).</span><span class="sxs-lookup"><span data-stu-id="40d10-124">For more information, see [Create Master Data Manager Web Service Proxy Classes](../develop/create-master-data-manager-web-service-proxy-classes.md).</span></span>  
  
-   <span data-ttu-id="40d10-125">Adicione usuários e grupos ao [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40d10-125">Add users and groups to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="40d10-126">Se nenhum usuário ou grupo tiver recebido autorização de acesso ao [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], você deverá abrir o [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] usando as credenciais de administrador do sistema [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40d10-126">If no users or groups have been granted access to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must open [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] using the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] system administrator credentials.</span></span> <span data-ttu-id="40d10-127">Para obter mais informações, veja [Administradores &#40;Master Data Services&#41;](../administrators-master-data-services.md) e [Usuários e grupos &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="40d10-127">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md) and [Users and Groups &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40d10-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="40d10-128">See Also</span></span>  
 <span data-ttu-id="40d10-129">[Instalar Master Data Services](install-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="40d10-129">[Install Master Data Services](install-master-data-services.md) </span></span>  
 [<span data-ttu-id="40d10-130">Página Configuração da Web &#40;Master Data Services Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="40d10-130">Web Configuration Page &#40;Master Data Services Configuration Manager&#41;</span></span>](../web-configuration-page-master-data-services-configuration-manager.md)  
  
  
