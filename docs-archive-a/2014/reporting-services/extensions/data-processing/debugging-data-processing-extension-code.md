---
title: Depurando o código de extensão de processamento de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- debugging data processing extensions [Reporting Services]
- troubleshooting [Reporting Services], data processing extensions
- data processing extensions [Reporting Services], debugging
ms.assetid: e963e205-9ae0-446d-97df-028a1d2727d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bf7490145f91ee8b3cfc2357c34010bed593ed9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572942"
---
# <a name="debugging-data-processing-extension-code"></a><span data-ttu-id="8f472-102">Depurando o código de extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="8f472-102">Debugging Data Processing Extension Code</span></span>
  <span data-ttu-id="8f472-103">O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] fornece várias ferramentas de depuração que podem ajudar você a analisar o código de extensão de processamento de dados e localizar erros nele.</span><span class="sxs-lookup"><span data-stu-id="8f472-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your data processing extension code and locate errors in it.</span></span> <span data-ttu-id="8f472-104">A ferramenta mais adequada dependerá do que você está tentando realizar.</span><span class="sxs-lookup"><span data-stu-id="8f472-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="8f472-105">Este exemplo usa o [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f472-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-data-processing-extension-code"></a><span data-ttu-id="8f472-106">Para depurar seu código de extensão de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="8f472-106">To debug your data processing extension code</span></span>  
  
1.  <span data-ttu-id="8f472-107">Inicie o [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] e abra seu projeto de extensão de processamento de dados.</span><span class="sxs-lookup"><span data-stu-id="8f472-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)], and open your data processing extension project.</span></span>  
  
2.  <span data-ttu-id="8f472-108">Crie o projeto e implante seu assembly de extensão de processamento de dados e o arquivo .pdb anexo ao Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="8f472-108">Build the project, and deploy your data processing extension assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="8f472-109">Para obter mais informações sobre a implantação, consulte [Como implantar uma extensão de processamento de dados no Designer de Relatórios](deploying-a-data-processing-extension-to-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="8f472-109">For more information about deployment, see [How to: Deploy a Data Processing Extension to Report Designer](deploying-a-data-processing-extension-to-report-designer.md).</span></span>  
  
3.  <span data-ttu-id="8f472-110">Abra um novo Projeto de Relatório no [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] enquanto deixa seu código de extensão de processamento de dados aberto em uma janela separada do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f472-110">Open a new Report Project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] while leaving your data processing extension code open in a separate window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="8f472-111">Navegue até a janela do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] que contém seu projeto de extensão de processamento de dados e defina alguns pontos de quebra em seu código.</span><span class="sxs-lookup"><span data-stu-id="8f472-111">Navigate to the window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] that contains your data processing extension project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="8f472-112">Com a janela do projeto de extensão de processamento de dados ainda ativa, clique em **Anexar ao Processo** no menu **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="8f472-112">With the data processing extension project window still active, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="8f472-113">A caixa de diálogo **Anexar ao Processo** será aberta.</span><span class="sxs-lookup"><span data-stu-id="8f472-113">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="8f472-114">Na lista de processos, selecione o processo devenv.exe que corresponde ao Projeto de Relatório e clique em **Anexar**.</span><span class="sxs-lookup"><span data-stu-id="8f472-114">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="8f472-115">Defina a fonte de dados do relatório usando a guia **Dados do Relatório** do Projeto de Relatório.</span><span class="sxs-lookup"><span data-stu-id="8f472-115">Define your report data source using the **Report Data** tab of the Report Project.</span></span> <span data-ttu-id="8f472-116">Você provavelmente usará o Designer de Consulta genérico para executar uma consulta na fonte de dados personalizada.</span><span class="sxs-lookup"><span data-stu-id="8f472-116">You will most likely use the generic Query Designer to execute a query against your custom data source.</span></span> <span data-ttu-id="8f472-117">Isso deve chamar o depurador e executar o código correspondente a seus pontos de quebra.</span><span class="sxs-lookup"><span data-stu-id="8f472-117">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="8f472-118">Percorra seu código usando a tecla F11.</span><span class="sxs-lookup"><span data-stu-id="8f472-118">Step through your code using the F11 key.</span></span> <span data-ttu-id="8f472-119">Para obter mais informações sobre como usar o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para depuração, consulte a documentação do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f472-119">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f472-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f472-120">See Also</span></span>  
 <span data-ttu-id="8f472-121">[Implantando uma extensão de processamento de dados](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="8f472-121">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="8f472-122">[Extensões do Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="8f472-122">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="8f472-123">[Implementando uma extensão de processamento de dados](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="8f472-123">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="8f472-124">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8f472-124">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
