---
title: Habilitar a integração do Data Quality Services com Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ab32938d-a80e-4106-80d4-94b2de3d67dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8d2fa25254cae2a129b6e08ff657d92af4ff9455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572121"
---
# <a name="enable-data-quality-services-integration-with-master-data-services"></a><span data-ttu-id="b789a-102">Habilitar a integração do Data Quality Services com Master Data Services</span><span class="sxs-lookup"><span data-stu-id="b789a-102">Enable Data Quality Services Integration with Master Data Services</span></span>
  <span data-ttu-id="b789a-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], a funcionalidade correspondente é fornecida pelo DQS (Data Quality Services).</span><span class="sxs-lookup"><span data-stu-id="b789a-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], matching functionality is provided by Data Quality Services (DQS).</span></span> <span data-ttu-id="b789a-104">Essa funcionalidade deve ser habilitada para ser usada.</span><span class="sxs-lookup"><span data-stu-id="b789a-104">This functionality must be enabled to be used.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b789a-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b789a-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="b789a-106">Um aplicativo Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] e banco de dados devem existir.</span><span class="sxs-lookup"><span data-stu-id="b789a-106">A [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web application and database must exist.</span></span>  
  
-   <span data-ttu-id="b789a-107">O recurso Data Quality Services e o Cliente Data Quality devem ser instalados na mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda o banco de dados do MDS.</span><span class="sxs-lookup"><span data-stu-id="b789a-107">The Data Quality Services feature and the Data Quality Client must be installed on the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the MDS database.</span></span> <span data-ttu-id="b789a-108">Para obter mais informações, consulte [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="b789a-108">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
### <a name="to-enable-data-quality-services-integration"></a><span data-ttu-id="b789a-109">Para habilitar a integração do Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="b789a-109">To enable Data Quality Services integration</span></span>  
  
1.  <span data-ttu-id="b789a-110">Abra o [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b789a-110">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="b789a-111">No painel esquerdo, clique em **Configuração da Web**.</span><span class="sxs-lookup"><span data-stu-id="b789a-111">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="b789a-112">Na página **Configuração da Web** , selecione o site e o aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="b789a-112">On the **Web Configuration** page, select the website and web application.</span></span>  
  
4.  <span data-ttu-id="b789a-113">Na seção **Habilitar Integração do DQS** , clique em **Habilitar integração com Data Quality Services**.</span><span class="sxs-lookup"><span data-stu-id="b789a-113">In the **Enable DQS Integration** section, click **Enable integration with Data Quality Services**.</span></span>  
  
5.  <span data-ttu-id="b789a-114">Na caixa de diálogo de confirmação, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b789a-114">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b789a-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b789a-115">See Also</span></span>  
 <span data-ttu-id="b789a-116">[Correspondência de qualidade de dados no Suplemento MDS para Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="b789a-116">[Data Quality Matching in the MDS Add-in for Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="b789a-117">[Suplemento do Master Data Services para Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span><span class="sxs-lookup"><span data-stu-id="b789a-117">[Master Data Services Add-in for Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span></span>  
 [<span data-ttu-id="b789a-118">Instalar o Master Data Services</span><span class="sxs-lookup"><span data-stu-id="b789a-118">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
