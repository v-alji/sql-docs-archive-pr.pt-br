---
title: Ativar a integração de recursos do PowerPivot para coleções de sites na administração central | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 62a27e53-446a-42d7-b5db-c009e02d4904
author: minewiskan
ms.author: owend
ms.openlocfilehash: b565434cba197d04327e833d4ac6eab3caf96646
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680079"
---
# <a name="activate-powerpivot-feature-integration-for-site-collections-in-central-administration"></a><span data-ttu-id="2501d-102">Ativar a integração de recursos do PowerPivot para coleções de sites na Administração Central</span><span class="sxs-lookup"><span data-stu-id="2501d-102">Activate PowerPivot Feature Integration for Site Collections in Central Administration</span></span>
  <span data-ttu-id="2501d-103">A ativação da integração de recursos do PowerPivot para coleções de sites específicas será necessária se você tiver usado a opção de instalação Farm Existente para instalar o SQL Server PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2501d-103">Activating PowerPivot feature integration for specific site collections is required if you used the Existing Farm installation option to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="2501d-104">Se você instalou o PowerPivot para SharePoint usando a opção Novo Servidor, poderá ignorar esta tarefa pois a Instalação do SQL Server já ativou a integração de recurso do PowerPivot para a coleção de sites raiz quando configurou sua implantação.</span><span class="sxs-lookup"><span data-stu-id="2501d-104">If you installed PowerPivot for SharePoint using the New Server option, you can skip this task because SQL Server Setup already activated PowerPivot feature integration for the root site collection when it configured your deployment.</span></span>  
  
 <span data-ttu-id="2501d-105">A ativação de recursos em nível de coleção de sites é necessária para tornar as páginas e os modelos disponíveis em seus sites, incluindo páginas de configuração para atualização de dados agendada e páginas de aplicativo para Galeria do PowerPivot e bibliotecas de Feed de Dados.</span><span class="sxs-lookup"><span data-stu-id="2501d-105">Feature activation at the site collection level is necessary to make application pages and templates available to your sites, including configuration pages for scheduled data refresh and application pages for PowerPivot Gallery and Data Feed libraries.</span></span>  
  
 <span data-ttu-id="2501d-106">Você deve ativar a integração do PowerPivot para cada conjunto de sites que dê suporte ao processamento de consultas do PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="2501d-106">You must activate PowerPivot integration for each site collection that supports PowerPivot query processing.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2501d-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2501d-107">Prerequisites</span></span>  
 <span data-ttu-id="2501d-108">Você deve ser um administrador de conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="2501d-108">You must be a site collection administrator.</span></span>  
  
## <a name="activate-powerpivot-features"></a><span data-ttu-id="2501d-109">Ativar os recursos do PowerPivot</span><span class="sxs-lookup"><span data-stu-id="2501d-109">Activate PowerPivot Features</span></span>  
  
1.  <span data-ttu-id="2501d-110">Em um site do SharePoint, clique em **Ações do Site**.</span><span class="sxs-lookup"><span data-stu-id="2501d-110">On a SharePoint site, click **Site Actions**.</span></span>  
  
     <span data-ttu-id="2501d-111">Por padrão, os aplicativos Web do SharePoint são acessados pela porta 80.</span><span class="sxs-lookup"><span data-stu-id="2501d-111">By default, SharePoint web applications are accessed through port 80.</span></span> <span data-ttu-id="2501d-112">Isso significa que você pode acessar frequentemente um site do SharePoint inserindo http://\<computer name> para abrir o conjunto de sites raiz.</span><span class="sxs-lookup"><span data-stu-id="2501d-112">This means that you can often access a SharePoint site by entering http://\<computer name> to open the root site collection.</span></span>  
  
2.  <span data-ttu-id="2501d-113">Clique em **Configurações de Site**.</span><span class="sxs-lookup"><span data-stu-id="2501d-113">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="2501d-114">Em Administração do Conjunto de Sites, clique em **Recursos do conjunto de sites**.</span><span class="sxs-lookup"><span data-stu-id="2501d-114">In Site Collection Administration, click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="2501d-115">Role a página até encontrar o **recurso de coleção de sites de integração do PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="2501d-115">Scroll down the page until you find **PowerPivot Integration Site Collection Feature**.</span></span>  
  
5.  <span data-ttu-id="2501d-116">Clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="2501d-116">Click **Activate**.</span></span>  
  
6.  <span data-ttu-id="2501d-117">Repita a operação em outros conjuntos de sites, abrindo cada site e clicando em **Ações do Site**.</span><span class="sxs-lookup"><span data-stu-id="2501d-117">Repeat for additional site collections by opening each site and clicking **Site Actions**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2501d-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2501d-118">See Also</span></span>  
 <span data-ttu-id="2501d-119">[Administração e configuração do servidor PowerPivot na administração central](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="2501d-119">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 <span data-ttu-id="2501d-120">[PowerPivot para SharePoint de configuração inicial &#40;&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="2501d-120">[Initial Configuration &#40;PowerPivot for SharePoint&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="2501d-121">Instalação do PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="2501d-121">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
