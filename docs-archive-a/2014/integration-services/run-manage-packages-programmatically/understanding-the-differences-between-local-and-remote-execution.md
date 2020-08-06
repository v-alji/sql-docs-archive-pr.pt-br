---
title: Compreender as diferenças entre execução local e remota | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- packages [Integration Services], troubleshooting
ms.assetid: 610ee7d9-4fea-4aba-9395-57add826923b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 399584c790f4c5a5dd136121c58a5ff7743f4969
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680034"
---
# <a name="understanding-the-differences-between-local-and-remote-execution"></a><span data-ttu-id="2de2a-102">Compreendendo as diferenças entre execução local e remota</span><span class="sxs-lookup"><span data-stu-id="2de2a-102">Understanding the Differences between Local and Remote Execution</span></span>
  <span data-ttu-id="2de2a-103">Desenvolvedores e administradores de pacotes devem ficar atentos às restrições relacionadas ao local de execução de um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2de2a-103">Package developers and administrators should be aware that there are restrictions related to where an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package runs.</span></span>  
  
-   <span data-ttu-id="2de2a-104">**Um pacote é executado no mesmo computador que o programa que o inicia**.</span><span class="sxs-lookup"><span data-stu-id="2de2a-104">**A package runs on the same computer as the program that launches it**.</span></span> <span data-ttu-id="2de2a-105">Mesmo quando um programa carrega um pacote que é armazenado remotamente em outro servidor, o pacote é executado no computador local.</span><span class="sxs-lookup"><span data-stu-id="2de2a-105">Even when a program loads a package that is stored remotely on another server, the package runs on the local computer.</span></span>  
  
-   <span data-ttu-id="2de2a-106">**Você só pode executar um pacote fora do ambiente de desenvolvimento em um computador que tem o Integration Services instalado**.</span><span class="sxs-lookup"><span data-stu-id="2de2a-106">**You can only run a package outside the development environment on a computer that has Integration Services installed**.</span></span> <span data-ttu-id="2de2a-107">Você não pode executar pacotes fora do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] em um computador cliente que não tenha o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instalado, e os termos do seu licenciamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] talvez não permitam que você instale o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] em computadores adicionais.</span><span class="sxs-lookup"><span data-stu-id="2de2a-107">You cannot run packages outside of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing may not permit you to install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> <span data-ttu-id="2de2a-108">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é um componente de servidor e não é redistribuível aos computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="2de2a-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is a server component and is not redistributable to client computers.</span></span> <span data-ttu-id="2de2a-109">Para executar pacotes de um computador cliente, procure iniciá-los de forma a garantir a execução dos pacotes no servidor.</span><span class="sxs-lookup"><span data-stu-id="2de2a-109">To run packages from a client computer, you need to launch them in a manner that ensures that the packages run on the server.</span></span>  
  
 <span data-ttu-id="2de2a-110">Para obter mais informações sobre como carregar e executar um pacote salvo, consulte:</span><span class="sxs-lookup"><span data-stu-id="2de2a-110">For more information about loading and running a saved package, see:</span></span>  
  
-   [<span data-ttu-id="2de2a-111">Carregar e executar um pacote local programaticamente</span><span class="sxs-lookup"><span data-stu-id="2de2a-111">Loading and Running a Local Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
  
-   [<span data-ttu-id="2de2a-112">Carregar e executar um pacote remoto programaticamente</span><span class="sxs-lookup"><span data-stu-id="2de2a-112">Loading and Running a Remote Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
  
 <span data-ttu-id="2de2a-113">Para obter mais informações sobre como executar um pacote e carregar sua saída em um programa personalizado, consulte:</span><span class="sxs-lookup"><span data-stu-id="2de2a-113">For more information about running a package and loading its output into a custom program, see:</span></span>  
  
-   [<span data-ttu-id="2de2a-114">Carregar a saída de um pacote local</span><span class="sxs-lookup"><span data-stu-id="2de2a-114">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
<span data-ttu-id="2de2a-115">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2de2a-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2de2a-116">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="2de2a-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2de2a-117">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="2de2a-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2de2a-118">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="2de2a-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de2a-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2de2a-119">See Also</span></span>  
 <span data-ttu-id="2de2a-120">[Carregando e executando um pacote local programaticamente](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="2de2a-120">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 <span data-ttu-id="2de2a-121">[Carregando e executando um pacote remoto programaticamente](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="2de2a-121">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="2de2a-122">Carregando a saída de um pacote local</span><span class="sxs-lookup"><span data-stu-id="2de2a-122">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
