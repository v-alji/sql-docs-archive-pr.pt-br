---
title: Contas de domínio necessárias para o farm do SharePoint (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 90cd6d3e-a271-4cb8-81f2-fc555b2d3cab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7d180fbc12a264256156c878916838f7caeec723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583350"
---
# <a name="domain-accounts-required-for-sharepoint-farm-upgrade-advisor"></a><span data-ttu-id="c804a-102">Contas de domínio necessárias ao farm do SharePoint (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="c804a-102">Domain accounts required for SharePoint farm (Upgrade Advisor)</span></span>
  <span data-ttu-id="c804a-103">Os produtos do SharePoint configurados para um ambiente de farm requerem o uso de contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="c804a-103">SharePoint products that are configured for a farm environment require that you use domain accounts.</span></span>  
  
||  
|-|  
|<span data-ttu-id="c804a-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c804a-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="c804a-105">Componente</span><span class="sxs-lookup"><span data-stu-id="c804a-105">Component</span></span>  
 [!INCLUDE[ssRS](../../includes/ssrs.md)]  
  
### <a name="description"></a><span data-ttu-id="c804a-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c804a-106">Description</span></span>  
 <span data-ttu-id="c804a-107">Os produtos do SharePoint configurados para um ambiente de farm requerem o uso de contas de domínio para conexões de serviços e bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="c804a-107">SharePoint products that are configured for a farm environment require that you use domain accounts for services and database connections.</span></span> <span data-ttu-id="c804a-108">Isso inclui a conta especificada para a conta de serviço do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c804a-108">This includes the account you have specified for the Reporting Services service account.</span></span>  
  
 <span data-ttu-id="c804a-109">Você encontrará problemas nas páginas de Administração Central do SharePoint 2010 se não estiver usando uma conta de usuário de domínio para o Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c804a-109">SharePoint 2010 Central Administration pages are one place you will see problems if you are not using a domain user account for Reporting Services.</span></span> <span data-ttu-id="c804a-110">Ao tentar configurar a integração do Reporting Services, você verá uma mensagem de erro similar ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="c804a-110">When you try to configure Reporting Services integration, you will see an error message similar to the following:</span></span>  
  
 <span data-ttu-id="c804a-111">"O servidor de relatório está sendo executado em uma conta NT AUTHORITY\NETWORK interna, que não tem suporte em uma instalação de farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c804a-111">"The report server is running under the built-in NT AUTHORITY\NETWORK SERVICE account, which is not supported by a SharePoint farm installation.</span></span> <span data-ttu-id="c804a-112">Reconfigure o servidor de relatório para ser executado em uma conta de domínio."</span><span class="sxs-lookup"><span data-stu-id="c804a-112">Please reconfigure the report server to run under a domain account."</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c804a-113">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="c804a-113">Corrective Action</span></span>  
 <span data-ttu-id="c804a-114">Para o [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e versões anteriores, use a Gerenciador de configurações do Reporting Services para alterar a conta atribuída como a conta de serviço do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c804a-114">For [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and previous versions, use the Reporting Services Configuration Manager to change the account that is assigned as the report server service account.</span></span>  
  
#### <a name="to-change-the-service-account-from-configuration-manager"></a><span data-ttu-id="c804a-115">Para alterar a conta de serviço no Gerenciador de Configuração</span><span class="sxs-lookup"><span data-stu-id="c804a-115">To change the service account from Configuration Manager</span></span>  
  
1.  <span data-ttu-id="c804a-116">No menu **Iniciar** , selecione **todos os programas**e, em seguida, clique em **Microsoft SQL Server 2008 R2**.</span><span class="sxs-lookup"><span data-stu-id="c804a-116">From the **Start** menu, select **All Programs**, and then click **Microsoft SQL Server 2008 R2**.</span></span>  
  
2.  <span data-ttu-id="c804a-117">Selecione **ferramentas de configuração**e, em seguida, clique em **Gerenciador de configurações do Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="c804a-117">Select **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="c804a-118">Em Configuration Manager, selecione a guia **conta de serviço** .</span><span class="sxs-lookup"><span data-stu-id="c804a-118">In Configuration Manager, select the **Service Account** tab.</span></span>  
  
4.  <span data-ttu-id="c804a-119">Selecione **usar outra conta** e insira as credenciais para uma conta de domínio.</span><span class="sxs-lookup"><span data-stu-id="c804a-119">Select **Use another account** and enter the credentials for a domain account.</span></span>  
  
5.  <span data-ttu-id="c804a-120">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c804a-120">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c804a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c804a-121">See Also</span></span>  
 [<span data-ttu-id="c804a-122">Configurar a conta de serviço do servidor de relatório &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="c804a-122">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
  
  
