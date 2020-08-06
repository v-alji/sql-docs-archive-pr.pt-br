---
title: Depurando o código de extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], debugging
- debugging delivery extensions [Reporting Services]
- troubleshooting [Reporting Services], delivery extensions
ms.assetid: a7d959da-5005-4a50-aca7-2cef36aa9947
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb80ac97f5c0e346b208784f1fa5b857ff93ef57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685427"
---
# <a name="debugging-delivery-extension-code"></a><span data-ttu-id="2485e-102">Depurando o código de extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="2485e-102">Debugging Delivery Extension Code</span></span>
  <span data-ttu-id="2485e-103">O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] fornece várias ferramentas de depuração que podem ajudar você a analisar seu código de extensão de entrega e localizar erros nele.</span><span class="sxs-lookup"><span data-stu-id="2485e-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your delivery extension code and locate errors in it.</span></span> <span data-ttu-id="2485e-104">A ferramenta mais adequada dependerá do que você está tentando realizar.</span><span class="sxs-lookup"><span data-stu-id="2485e-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="2485e-105">Este exemplo usa o [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2485e-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-delivery-extension-code"></a><span data-ttu-id="2485e-106">Para depurar seu código de extensão de entrega</span><span class="sxs-lookup"><span data-stu-id="2485e-106">To debug your delivery extension code</span></span>  
  
1.  <span data-ttu-id="2485e-107">Inicie o [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] e abra o projeto de extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="2485e-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] and open your delivery extension project.</span></span>  
  
2.  <span data-ttu-id="2485e-108">Crie o projeto e implante o seu assembly de extensão de entrega e o arquivo .pdb que o acompanha no servidor de relatório e no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="2485e-108">Build the project and deploy your delivery extension assembly and the accompanying .pdb file to the report server and Report Manager.</span></span> <span data-ttu-id="2485e-109">Para obter mais informações sobre a implantação, consulte [Implantando uma extensão de entrega](deploying-a-delivery-extension.md).</span><span class="sxs-lookup"><span data-stu-id="2485e-109">For more information about deployment, see [Deploying a Delivery Extension](deploying-a-delivery-extension.md).</span></span>  
  
3.  <span data-ttu-id="2485e-110">Se você escreveu uma interface do usuário de assinatura para estender o Gerenciador de Relatórios, abra o Internet Explorer e navegue até o Gerenciador de Relatórios deixando o seu código de extensão de entrega aberto no [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2485e-110">If you have written a subscription user interface to extend Report Manager, open Internet Explorer and navigate to Report Manager while leaving your delivery extension code open in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="2485e-111">Se você não possui uma interface do usuário de assinatura implantada para o Gerenciador de Relatórios, basta abrir o aplicativo cliente, de onde chamará a sua extensão de entrega usando a API SOAP.</span><span class="sxs-lookup"><span data-stu-id="2485e-111">If you do not have a subscription user interface deployed for Report Manager, simply open the client application from which you call your delivery extension using the SOAP API.</span></span>  
  
4.  <span data-ttu-id="2485e-112">Navegue até o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] e até o seu projeto de extensão de entrega e defina alguns pontos de quebra em seu código.</span><span class="sxs-lookup"><span data-stu-id="2485e-112">Navigate to [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] and your delivery extension project, and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="2485e-113">Com o projeto de extensão de entrega ainda na janela ativa, clique em **Anexar ao Processo** no menu **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="2485e-113">With the delivery extension project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="2485e-114">A caixa de diálogo **Anexar ao Processo** será aberta.</span><span class="sxs-lookup"><span data-stu-id="2485e-114">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="2485e-115">Na lista de processos, selecione o processo aspnet_wp.exe (ou w3wp.exe, se o aplicativo tiver sido implantado no IIS 6.0) e clique em **Anexar**.</span><span class="sxs-lookup"><span data-stu-id="2485e-115">From the list of processes, select the aspnet_wp.exe process (or w3wp.exe if your application is deployed on IIS 6.0), and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="2485e-116">Defina uma assinatura nova usando a sua extensão de entrega.</span><span class="sxs-lookup"><span data-stu-id="2485e-116">Define a new subscription using your delivery extension.</span></span> <span data-ttu-id="2485e-117">É bem provável que você use o Gerenciador de Relatórios ou a API SOAP.</span><span class="sxs-lookup"><span data-stu-id="2485e-117">You will most likely use Report Manager or the SOAP API.</span></span> <span data-ttu-id="2485e-118">Isso deve chamar o depurador e executar o código correspondente a seus pontos de quebra.</span><span class="sxs-lookup"><span data-stu-id="2485e-118">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="2485e-119">Percorra o código usando a tecla **F11**.</span><span class="sxs-lookup"><span data-stu-id="2485e-119">Step through your code using the **F11** key.</span></span> <span data-ttu-id="2485e-120">Para obter mais informações sobre como usar o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para depuração, consulte a documentação do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2485e-120">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2485e-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2485e-121">See Also</span></span>  
 <span data-ttu-id="2485e-122">[Implementando uma extensão de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="2485e-122">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="2485e-123">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2485e-123">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
