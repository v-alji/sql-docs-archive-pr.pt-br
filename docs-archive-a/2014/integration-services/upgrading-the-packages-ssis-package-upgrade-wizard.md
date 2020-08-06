---
title: Atualizando os pacotes (Assistente de atualização de pacotes SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.upgradingpackage.f1
ms.assetid: cdb842e3-2e59-4ede-b127-be4fde46875c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d13228dabc1566b592733da4afd8ebde3671ee0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570743"
---
# <a name="upgrading-the-packages-ssis-package-upgrade-wizard"></a><span data-ttu-id="81feb-102">Atualizando os pacotes (Assistente de Atualização de Pacotes SSIS)</span><span class="sxs-lookup"><span data-stu-id="81feb-102">Upgrading the Packages (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="81feb-103">Use a página **Atualizando os Pacotes** para exibir o progresso da atualização de pacotes e para interromper o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="81feb-103">Use the **Upgrading the Packages** page to view the progress of package upgrade and to interrupt the upgrade process.</span></span> <span data-ttu-id="81feb-104">O Assistente de Atualização de Pacotes [!INCLUDE[ssIS](../includes/ssis-md.md)] atualiza os pacotes selecionados um por um.</span><span class="sxs-lookup"><span data-stu-id="81feb-104">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard upgrades the selected packages one by one.</span></span>  
  
 <span data-ttu-id="81feb-105">**Para exibir os pacotes atualizados que foram salvos em um banco de dados do SQL Server ou no armazenamento de pacotes**</span><span class="sxs-lookup"><span data-stu-id="81feb-105">**To view upgraded packages that were saved to a SQL Server database or to the package store**</span></span>  
  
-   <span data-ttu-id="81feb-106">No [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], em Pesquisador de Objetos, conecte-se à instância local do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]e expanda o nó **Pacotes Armazenados** para saber quais pacotes foram atualizados.</span><span class="sxs-lookup"><span data-stu-id="81feb-106">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], in Object Explorer, connect to the local instance of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], and then expand the **Stored Packages** node to see the packages that were upgraded.</span></span>  
  
 <span data-ttu-id="81feb-107">**Para exibir os pacotes atualizados que foram atualizados nas Ferramentas de Dados do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="81feb-107">**To view upgraded packages that were upgraded from SQL Server Data Tools**</span></span>  
  
-   <span data-ttu-id="81feb-108">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], em Gerenciador de Soluções, abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e expanda o nó **Pacotes SSIS** para ver os pacotes atualizados.</span><span class="sxs-lookup"><span data-stu-id="81feb-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and then expand the **SSIS Packages** node to see the upgraded packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="81feb-109">Opções</span><span class="sxs-lookup"><span data-stu-id="81feb-109">Options</span></span>  
 <span data-ttu-id="81feb-110">**Painel de mensagens**</span><span class="sxs-lookup"><span data-stu-id="81feb-110">**Message pane**</span></span>  
 <span data-ttu-id="81feb-111">Exibe mensagens de progresso e informações de resumo durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="81feb-111">Displays progress messages and summary information during the upgrade process.</span></span>  
  
 <span data-ttu-id="81feb-112">**Ação**</span><span class="sxs-lookup"><span data-stu-id="81feb-112">**Action**</span></span>  
 <span data-ttu-id="81feb-113">Exibe as ações na atualização.</span><span class="sxs-lookup"><span data-stu-id="81feb-113">View the actions in the upgrade.</span></span>  
  
 <span data-ttu-id="81feb-114">**Status**</span><span class="sxs-lookup"><span data-stu-id="81feb-114">**Status**</span></span>  
 <span data-ttu-id="81feb-115">Exibe o resultado de cada ação.</span><span class="sxs-lookup"><span data-stu-id="81feb-115">View the result of each action.</span></span>  
  
 <span data-ttu-id="81feb-116">**Message**</span><span class="sxs-lookup"><span data-stu-id="81feb-116">**Message**</span></span>  
 <span data-ttu-id="81feb-117">Exibe as mensagens de erro que cada ação gera.</span><span class="sxs-lookup"><span data-stu-id="81feb-117">View the error messages that each action generates.</span></span>  
  
 <span data-ttu-id="81feb-118">**Parar**</span><span class="sxs-lookup"><span data-stu-id="81feb-118">**Stop**</span></span>  
 <span data-ttu-id="81feb-119">Pare a atualização do pacote.</span><span class="sxs-lookup"><span data-stu-id="81feb-119">Stop the package upgrade.</span></span>  
  
 <span data-ttu-id="81feb-120">**Report**</span><span class="sxs-lookup"><span data-stu-id="81feb-120">**Report**</span></span>  
 <span data-ttu-id="81feb-121">Selecione o que deseja fazer com o relatório que contém os resultados da atualização do pacote:</span><span class="sxs-lookup"><span data-stu-id="81feb-121">Select what you want to do with the report that contains the results of the package upgrade:</span></span>  
  
-   <span data-ttu-id="81feb-122">Exiba o relatório online.</span><span class="sxs-lookup"><span data-stu-id="81feb-122">View the report online.</span></span>  
  
-   <span data-ttu-id="81feb-123">Salve o relatório em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="81feb-123">Save the report to a file.</span></span>  
  
-   <span data-ttu-id="81feb-124">Copie o relatório na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="81feb-124">Copy the report to the Clipboard</span></span>  
  
-   <span data-ttu-id="81feb-125">Envie o relatório como uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="81feb-125">Send the report as an e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81feb-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81feb-126">See Also</span></span>  
 [<span data-ttu-id="81feb-127">Atualizar pacotes do Integration Services</span><span class="sxs-lookup"><span data-stu-id="81feb-127">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
