---
title: Instalar o SQL Server 2014 no Server Core | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 1dd294cc-5b69-4d0c-9005-3e307b75678b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2614c43bb763757db7db46b1c7a966221da96f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679508"
---
# <a name="install-sql-server-2014-on-server-core"></a><span data-ttu-id="96945-102">Instalar o SQL Server 2014 no Server Core</span><span class="sxs-lookup"><span data-stu-id="96945-102">Install SQL Server 2014 on Server Core</span></span>
  <span data-ttu-id="96945-103">Você pode instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em uma instalação do Server Core do [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 ou do [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-103">You can install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="96945-104">Este tópico apresenta detalhes de configuração específicos sobre a instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] no Server Core.</span><span class="sxs-lookup"><span data-stu-id="96945-104">This topic provides setup-specific details for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core.</span></span>  
  
 <span data-ttu-id="96945-105">A opção de instalação do Server Core para o sistema operacional [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] oferece um ambiente mínimo para a execução de funções de servidor específicas.</span><span class="sxs-lookup"><span data-stu-id="96945-105">The Server Core installation option for the [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] operating system provides a minimal environment for running specific server roles.</span></span> <span data-ttu-id="96945-106">Isso ajuda a reduzir os requisitos de manutenção e gerenciamento e a superfície de ataque para essas funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="96945-106">This helps to reduce maintenance and management requirements and the attack surface for those server roles.</span></span> <span data-ttu-id="96945-107">Para obter mais informações sobre o Server Core conforme implementado em [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] , consulte [Server Core para Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) ( https://go.microsoft.com/fwlink/?LinkId=202439) .</span><span class="sxs-lookup"><span data-stu-id="96945-107">For more information on Server Core as implemented on [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)], see [Server Core for Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) (https://go.microsoft.com/fwlink/?LinkId=202439).</span></span> <span data-ttu-id="96945-108">Para obter mais informações sobre o Server Core implementado no [!INCLUDE[win8srv](../../includes/win8srv-md.md)], consulte [Server Core para Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx) ).</span><span class="sxs-lookup"><span data-stu-id="96945-108">For more information on Server Core as implemented on [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Server Core for Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="96945-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="96945-109">Prerequisites</span></span>  
  
|<span data-ttu-id="96945-110">Requisito</span><span class="sxs-lookup"><span data-stu-id="96945-110">Requirement</span></span>|<span data-ttu-id="96945-111">Como instalar o</span><span class="sxs-lookup"><span data-stu-id="96945-111">How to install</span></span>|  
|-----------------|--------------------|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="96945-112">2.0 SP2</span><span class="sxs-lookup"><span data-stu-id="96945-112">2.0 SP2</span></span>|<span data-ttu-id="96945-113">Incluído na instalação do Server Core do [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 e do [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-113">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="96945-114">Se essa opção não estiver habilitada, ela será habilitada por padrão pela Instalação.</span><span class="sxs-lookup"><span data-stu-id="96945-114">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="96945-115">Não é possível executar as versões 2.0, 3.0 e 3.5 lado a lado em um computador.</span><span class="sxs-lookup"><span data-stu-id="96945-115">It is not possible to run versions 2.0, 3.0, and 3.5 side by side on a computer.</span></span> <span data-ttu-id="96945-116">Ao instalar o .NET Framework 3.5 SP1, você obtém as camadas de 2.0 e 3.0 automaticamente.</span><span class="sxs-lookup"><span data-stu-id="96945-116">When you install the .NET Framework 3.5 SP1, you get the 2.0 and 3.0 layers automatically.</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="96945-117">3.5 SP1 Full Profile</span><span class="sxs-lookup"><span data-stu-id="96945-117">3.5 SP1 Full Profile</span></span>|<span data-ttu-id="96945-118">Incluído na instalação do Server Core do [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="96945-118">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span> <span data-ttu-id="96945-119">Se essa opção não estiver habilitada, ela será habilitada por padrão pela Instalação.</span><span class="sxs-lookup"><span data-stu-id="96945-119">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="96945-120">Em um computador com o sistema operacional Windows, você deverá baixar e instalar o .NET Framework 3.5 SP1 antes de executar a Instalação, para instalar os componentes dependentes do .NET 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="96945-120">On a computer with Windows server operating system you must download and install .NET Framework 3.5 SP1 before you run Setup, to install components dependent on .NET 3.5 SP1.</span></span><br /><br /> <span data-ttu-id="96945-121">Para obter mais informações sobre as recomendações e diretrizes sobre como adquirir e habilitar o .NET Framework 3,5 no [!INCLUDE[win8srv](../../includes/win8srv-md.md)] , consulte [considerações de implantação do Microsoft .NET Framework 3,5](https://msdn.microsoft.com/library/windows/hardware/hh975396) ( https://msdn.microsoft.com/library/windows/hardware/hh975396) .</span><span class="sxs-lookup"><span data-stu-id="96945-121">For more information about the recommendations and guidance on how to acquire and enable .NET Framework 3.5 in [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Microsoft .NET Framework 3.5 Deployment Considerations](https://msdn.microsoft.com/library/windows/hardware/hh975396) (https://msdn.microsoft.com/library/windows/hardware/hh975396).</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="96945-122">4 Server Core Profile</span><span class="sxs-lookup"><span data-stu-id="96945-122">4 Server Core Profile</span></span>|<span data-ttu-id="96945-123">Para todas as edições do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , exceto [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], a Instalação instala o [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile como pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="96945-123">For all editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], Setup installs the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile as a prerequisite.</span></span><br /><br /> <span data-ttu-id="96945-124">Para [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)] o, baixe o [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] perfil do 4 Server Core do [Microsoft .NET Framework 4 (instalador autônomo) para o Server Core](https://www.microsoft.com/download/details.aspx?id=17718) ( https://www.microsoft.com/download/details.aspx?id=17718) e instale-o antes de prosseguir com a instalação.</span><span class="sxs-lookup"><span data-stu-id="96945-124">For [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)], download the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile from [Microsoft .NET Framework 4 (Standalone Installer) for Server Core](https://www.microsoft.com/download/details.aspx?id=17718) (https://www.microsoft.com/download/details.aspx?id=17718), and install it before you proceed with the setup.</span></span>|  
|<span data-ttu-id="96945-125">Windows Installer 4.5</span><span class="sxs-lookup"><span data-stu-id="96945-125">Windows Installer 4.5</span></span>|<span data-ttu-id="96945-126">Enviado com a instalação do Server Core do [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 e do [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-126">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
|<span data-ttu-id="96945-127">Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="96945-127">Windows PowerShell 2.0</span></span>|<span data-ttu-id="96945-128">Enviado com a instalação do Server Core do [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 e do [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-128">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
  
##  <a name="supported-features"></a><a name="BK_SupportedFeatures"></a> <span data-ttu-id="96945-129">Recursos com suporte</span><span class="sxs-lookup"><span data-stu-id="96945-129">Supported Features</span></span>  
 <span data-ttu-id="96945-130">Use a tabela a seguir para descobrir quais recursos têm suporte no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] em uma instalação do Server Core do [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 e do [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-130">Use the following table to find which features are supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|<span data-ttu-id="96945-131">Recurso</span><span class="sxs-lookup"><span data-stu-id="96945-131">Feature</span></span>|<span data-ttu-id="96945-132">Com suporte</span><span class="sxs-lookup"><span data-stu-id="96945-132">Supported</span></span>|  
|-------------|---------------|  
|[!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="96945-133">Serviços</span><span class="sxs-lookup"><span data-stu-id="96945-133">Services</span></span>|<span data-ttu-id="96945-134">Sim</span><span class="sxs-lookup"><span data-stu-id="96945-134">Yes</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="96945-135">Replicação</span><span class="sxs-lookup"><span data-stu-id="96945-135">Replication</span></span>|<span data-ttu-id="96945-136">Sim</span><span class="sxs-lookup"><span data-stu-id="96945-136">Yes</span></span>|  
|<span data-ttu-id="96945-137">Pesquisa de Texto Completo</span><span class="sxs-lookup"><span data-stu-id="96945-137">Full Text Search</span></span>|<span data-ttu-id="96945-138">Sim</span><span class="sxs-lookup"><span data-stu-id="96945-138">Yes</span></span>|  
|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]|<span data-ttu-id="96945-139">Sim</span><span class="sxs-lookup"><span data-stu-id="96945-139">Yes</span></span>|  
|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|<span data-ttu-id="96945-140">Não</span><span class="sxs-lookup"><span data-stu-id="96945-140">No</span></span>|  
|<span data-ttu-id="96945-141">SSDT ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Data Tools)</span><span class="sxs-lookup"><span data-stu-id="96945-141">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Data Tools (SSDT)</span></span>|<span data-ttu-id="96945-142">Não</span><span class="sxs-lookup"><span data-stu-id="96945-142">No</span></span>|  
|<span data-ttu-id="96945-143">Conectividade das ferramentas de cliente</span><span class="sxs-lookup"><span data-stu-id="96945-143">Client Tools Connectivity</span></span>|<span data-ttu-id="96945-144">Sim</span><span class="sxs-lookup"><span data-stu-id="96945-144">Yes</span></span>|  
|<span data-ttu-id="96945-145">Servidor Integration Services<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="96945-145">Integration Services Server<sup>[1]</sup></span></span>|<span data-ttu-id="96945-146">Sim</span><span class="sxs-lookup"><span data-stu-id="96945-146">Yes</span></span>|  
|<span data-ttu-id="96945-147">Compatibilidade das ferramentas de cliente com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="96945-147">Client Tools Backward Compatibility</span></span>|<span data-ttu-id="96945-148">Não</span><span class="sxs-lookup"><span data-stu-id="96945-148">No</span></span>|  
|<span data-ttu-id="96945-149">SDK de Ferramentas de cliente</span><span class="sxs-lookup"><span data-stu-id="96945-149">Client Tools SDK</span></span>|<span data-ttu-id="96945-150">Não</span><span class="sxs-lookup"><span data-stu-id="96945-150">No</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="96945-151">Manuais Online</span><span class="sxs-lookup"><span data-stu-id="96945-151">Books Online</span></span>|<span data-ttu-id="96945-152">Não</span><span class="sxs-lookup"><span data-stu-id="96945-152">No</span></span>|  
|<span data-ttu-id="96945-153">Ferramentas de Gerenciamento - Básicas</span><span class="sxs-lookup"><span data-stu-id="96945-153">Management Tools - Basic</span></span>|<span data-ttu-id="96945-154">Somente remoto<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="96945-154">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="96945-155">Ferramentas de Gerenciamento – Completas</span><span class="sxs-lookup"><span data-stu-id="96945-155">Management Tools - Complete</span></span>|<span data-ttu-id="96945-156">Somente remoto<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="96945-156">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="96945-157">Distributed Replay Controller</span><span class="sxs-lookup"><span data-stu-id="96945-157">Distributed Replay Controller</span></span>|<span data-ttu-id="96945-158">Não</span><span class="sxs-lookup"><span data-stu-id="96945-158">No</span></span>|  
|<span data-ttu-id="96945-159">Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="96945-159">Distributed Replay Client</span></span>|<span data-ttu-id="96945-160">Somente remoto<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="96945-160">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="96945-161">SDK de Conectividade de Cliente do SQL</span><span class="sxs-lookup"><span data-stu-id="96945-161">SQL Client Connectivity SDK</span></span>|<span data-ttu-id="96945-162">Sim</span><span class="sxs-lookup"><span data-stu-id="96945-162">Yes</span></span>|  
|<span data-ttu-id="96945-163">Microsoft Sync Framework</span><span class="sxs-lookup"><span data-stu-id="96945-163">Microsoft Sync Framework</span></span>|<span data-ttu-id="96945-164">Sim<sup>[3]</sup></span><span class="sxs-lookup"><span data-stu-id="96945-164">Yes<sup>[3]</sup></span></span>|  
|[!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]|<span data-ttu-id="96945-165">Não</span><span class="sxs-lookup"><span data-stu-id="96945-165">No</span></span>|  
|[!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]|<span data-ttu-id="96945-166">Não</span><span class="sxs-lookup"><span data-stu-id="96945-166">No</span></span>|  
  
 <span data-ttu-id="96945-167"><sup>[1]</sup> Para obter mais informações sobre o novo Integration Services Server e seus recursos no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , consulte [Integration Services &#40;SSIS&#41; Server](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="96945-167"><sup>[1]</sup>For more information about the new Integration Services Server and its features in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Integration Services &#40;SSIS&#41; Server](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="96945-168"><sup>[2]</sup> Não há suporte para a instalação desses recursos no Server Core.</span><span class="sxs-lookup"><span data-stu-id="96945-168"><sup>[2]</sup>Installation of these features on Server Core is not supported.</span></span> <span data-ttu-id="96945-169">Esses componentes podem ser instalados em um servidor diferente, que não seja o [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 ou o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, e conectados aos serviços de [!INCLUDE[ssDE](../../includes/ssde-md.md)] instalados no Server Core.</span><span class="sxs-lookup"><span data-stu-id="96945-169">These components can be installed on a different server that is not [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, and connected to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] services installed on Server Core.</span></span>  
  
 <span data-ttu-id="96945-170"><sup>[3]</sup> O Microsoft Sync Framework não está incluído no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pacote de instalação.</span><span class="sxs-lookup"><span data-stu-id="96945-170"><sup>[3]</sup>Microsoft Sync Framework is not included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation package.</span></span> <span data-ttu-id="96945-171">Você pode baixar a versão apropriada do Sync Framework deste [centro de download da Microsoft](https://go.microsoft.com/fwlink/?LinkId=221788) ( https://go.microsoft.com/fwlink/?LinkId=221788) página e instalá-la em um computador que esteja executando a instalação do Server Core do [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96945-171">You can download the appropriate version of Sync Framework from this [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=221788) (https://go.microsoft.com/fwlink/?LinkId=221788) page and install it on a computer that is running Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
## <a name="supported-scenario-matrix"></a><span data-ttu-id="96945-172">Matriz de cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="96945-172">Supported Scenario Matrix</span></span>  
 <span data-ttu-id="96945-173">A tabela a seguir mostra a matriz de cenários com suporte para a instalação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] em uma instalação do Server Core do [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 e do [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-173">The following table shows the supported scenario matrix for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96945-174">Edições do[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96945-174">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] editions</span></span>|<span data-ttu-id="96945-175">Todas as [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] edições de 64 bits<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="96945-175">All [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 64-bit editions<sup>[1]</sup></span></span>|  
|<span data-ttu-id="96945-176">Idioma do[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96945-176">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] language</span></span>|<span data-ttu-id="96945-177">Todos os idiomas</span><span class="sxs-lookup"><span data-stu-id="96945-177">All languages</span></span>|  
|<span data-ttu-id="96945-178">Idioma do[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na combinação de idioma/localidade do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="96945-178">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] language on OS language/locale (combination)</span></span>|<span data-ttu-id="96945-179">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em inglês no Windows em japonês</span><span class="sxs-lookup"><span data-stu-id="96945-179">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on JPN (Japanese) Windows</span></span><br /><br /> <span data-ttu-id="96945-180">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em inglês no Windows em alemão</span><span class="sxs-lookup"><span data-stu-id="96945-180">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on GER (German) Windows</span></span><br /><br /> <span data-ttu-id="96945-181">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em inglês no Windows em chinês</span><span class="sxs-lookup"><span data-stu-id="96945-181">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on CHS (Chinese-China) Windows</span></span><br /><br /> <span data-ttu-id="96945-182">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em inglês no Windows em árabe</span><span class="sxs-lookup"><span data-stu-id="96945-182">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ARA (Arabic (SA)) Windows</span></span><br /><br /> <span data-ttu-id="96945-183">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em inglês no Windows em tailandês</span><span class="sxs-lookup"><span data-stu-id="96945-183">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on THA (Thai) Windows</span></span><br /><br /> <span data-ttu-id="96945-184">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em inglês no Windows em turco</span><span class="sxs-lookup"><span data-stu-id="96945-184">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on TRK (Turkish) Windows</span></span><br /><br /> <span data-ttu-id="96945-185">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em inglês no Windows em português (Portugal)</span><span class="sxs-lookup"><span data-stu-id="96945-185">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on pt-PT (Portuguese Portugal) Windows</span></span><br /><br /> <span data-ttu-id="96945-186">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em inglês no Windows em inglês</span><span class="sxs-lookup"><span data-stu-id="96945-186">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ENG (English) Windows</span></span>|  
|<span data-ttu-id="96945-187">Windows Edition</span><span class="sxs-lookup"><span data-stu-id="96945-187">Windows edition</span></span>|[!INCLUDE[win8srv](../../includes/win8srv-md.md)] <span data-ttu-id="96945-188">64 bits x64 Datacenter</span><span class="sxs-lookup"><span data-stu-id="96945-188">64-bit x64 Datacenter</span></span><br /><br /> [!INCLUDE[win8srv](../../includes/win8srv-md.md)] <span data-ttu-id="96945-189">64 bits x64 Standard</span><span class="sxs-lookup"><span data-stu-id="96945-189">64-bit x64 Standard</span></span><br /><br /> <span data-ttu-id="96945-190">Server Core do[!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 64 bits x64 Data Center</span><span class="sxs-lookup"><span data-stu-id="96945-190">[!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 64-bit x64 Data Center Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="96945-191">Server Core do SP1 64 bits x64 Enterprise</span><span class="sxs-lookup"><span data-stu-id="96945-191">SP1 64-bit x64 Enterprise Server Core</span></span><br /><br /> <span data-ttu-id="96945-192">Server Core do[!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 64 bits x64 Standard</span><span class="sxs-lookup"><span data-stu-id="96945-192">[!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 64-bit x64 Standard Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="96945-193">Server Core do SP1 64 bits x64 Web</span><span class="sxs-lookup"><span data-stu-id="96945-193">SP1 64-bit x64 Web Server Core</span></span>|  
  
 <span data-ttu-id="96945-194"><sup>[1]</sup> Não há suporte para a instalação da versão de 32 bits das [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] edições no Server Core.</span><span class="sxs-lookup"><span data-stu-id="96945-194"><sup>[1]</sup>Installing the 32-bit version of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] editions is not supported on Server Core.</span></span>  
  
## <a name="upgrading"></a><span data-ttu-id="96945-195">Atualizando</span><span class="sxs-lookup"><span data-stu-id="96945-195">Upgrading</span></span>  
 <span data-ttu-id="96945-196">Em instalações do Server Core, atualizar de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] para [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] tem suporte.</span><span class="sxs-lookup"><span data-stu-id="96945-196">On Server Core installations, upgrading from [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is supported.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="96945-197">Instalação</span><span class="sxs-lookup"><span data-stu-id="96945-197">Installation</span></span>  
 <span data-ttu-id="96945-198">O[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] não tem suporte para a instalação por meio do assistente de instalação no sistema operacional Server Core.</span><span class="sxs-lookup"><span data-stu-id="96945-198">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] does not support setup by using the installation wizard on the Server Core operating system.</span></span> <span data-ttu-id="96945-199">Quando você faz a instalação no Server Core, a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte ao modo silencioso completo usando o parâmetro /Q ou o modo Silencioso Simples usando o parâmetro /QS.</span><span class="sxs-lookup"><span data-stu-id="96945-199">When installing on Server Core, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup supports full quiet mode by using the /Q parameter, or Quiet Simple mode by using the /QS parameter.</span></span> <span data-ttu-id="96945-200">Para obter mais informações, consulte [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) (Instalar o SQL Server 2014 do Prompt de Comando).</span><span class="sxs-lookup"><span data-stu-id="96945-200">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="96945-201">Não é possível instalar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] lado a lado com versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um computador executando o [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span><span class="sxs-lookup"><span data-stu-id="96945-201">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] cannot be installed side-by-side with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span></span>  
  
 <span data-ttu-id="96945-202">Independentemente do método de instalação, é necessário confirmar a aceitação dos termos da licença de software como indivíduo ou em nome de uma entidade, a menos que o uso do software seja governado por um contrato separado, como um contrato de licenciamento por volume da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou um contrato de terceiros com um ISV ou OEM.</span><span class="sxs-lookup"><span data-stu-id="96945-202">Regardless of the installation method, you are required to confirm acceptance of the software license terms as an individual or on behalf of an entity, unless your use of the software is governed by a separate agreement such as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing agreement or a third-party agreement with an ISV or OEM.</span></span>  
  
 <span data-ttu-id="96945-203">Os termos da licença são exibidos para exame e aceitação na interface do usuário da Instalação.</span><span class="sxs-lookup"><span data-stu-id="96945-203">The license terms are displayed for review and acceptance in the Setup user interface.</span></span> <span data-ttu-id="96945-204">As instalações autônomas (usando o parâmetro /Q ou /QS) devem incluir o parâmetro /IACCEPTSQLSERVERLICENSETERMS.</span><span class="sxs-lookup"><span data-stu-id="96945-204">Unattended installations (using the /Q or /QS parameters) must include the /IACCEPTSQLSERVERLICENSETERMS parameter.</span></span> <span data-ttu-id="96945-205">Você pode analisar as condições de licença separadamente em [Microsoft Software License Terms](https://go.microsoft.com/fwlink/?LinkId=148209)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="96945-205">You can review the license terms separately at [Microsoft Software License Terms](https://go.microsoft.com/fwlink/?LinkId=148209).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96945-206">Dependendo de como você recebeu o software (por exemplo, por meio de licenciamento por volume da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ), o uso do software pode estar sujeito a termos e condições adicionais.</span><span class="sxs-lookup"><span data-stu-id="96945-206">Depending on how you received the software (for example, through [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing), your use of the software may be subject to additional terms and conditions.</span></span>  
  
 <span data-ttu-id="96945-207">Para instalar recursos específicos, use o parâmetro /FEATURES e especifique o recurso pai ou os valores de recursos.</span><span class="sxs-lookup"><span data-stu-id="96945-207">To install specific features, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="96945-208">Para obter mais informações sobre os parâmetros de recursos e seu uso, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="96945-208">For more information about feature parameters and their use, see the following sections.</span></span>  
  
### <a name="feature-parameters"></a><span data-ttu-id="96945-209">Parâmetros de recursos</span><span class="sxs-lookup"><span data-stu-id="96945-209">Feature Parameters</span></span>  
  
|<span data-ttu-id="96945-210">Parâmetro de recurso</span><span class="sxs-lookup"><span data-stu-id="96945-210">Feature parameter</span></span>|<span data-ttu-id="96945-211">Descrição</span><span class="sxs-lookup"><span data-stu-id="96945-211">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="96945-212">SQLENGINE</span><span class="sxs-lookup"><span data-stu-id="96945-212">SQLENGINE</span></span>|<span data-ttu-id="96945-213">Instala apenas o [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-213">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="96945-214">REPLICAÇÃO</span><span class="sxs-lookup"><span data-stu-id="96945-214">REPLICATION</span></span>|<span data-ttu-id="96945-215">Instala o componente Replicação juntamente com o [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-215">Installs the Replication component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="96945-216">FULLTEXT</span><span class="sxs-lookup"><span data-stu-id="96945-216">FULLTEXT</span></span>|<span data-ttu-id="96945-217">Instala o componente FullText com o [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-217">Installs the FullText component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="96945-218">AS</span><span class="sxs-lookup"><span data-stu-id="96945-218">AS</span></span>|<span data-ttu-id="96945-219">Instala todos os componentes do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96945-219">Installs all [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="96945-220">IS</span><span class="sxs-lookup"><span data-stu-id="96945-220">IS</span></span>|<span data-ttu-id="96945-221">Instala todos os componentes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96945-221">Installs all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="96945-222">CONN</span><span class="sxs-lookup"><span data-stu-id="96945-222">CONN</span></span>|<span data-ttu-id="96945-223">Instala os componentes de conectividade.</span><span class="sxs-lookup"><span data-stu-id="96945-223">Installs the connectivity components.</span></span>|  
  
 <span data-ttu-id="96945-224">Veja os exemplos a seguir do uso de parâmetros de recurso:</span><span class="sxs-lookup"><span data-stu-id="96945-224">See the following examples of the usage of feature parameters:</span></span>  
  
|<span data-ttu-id="96945-225">Parâmetro e valores</span><span class="sxs-lookup"><span data-stu-id="96945-225">Parameter and values</span></span>|<span data-ttu-id="96945-226">Descrição</span><span class="sxs-lookup"><span data-stu-id="96945-226">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="96945-227">/FEATURES=SQLEngine</span><span class="sxs-lookup"><span data-stu-id="96945-227">/FEATURES=SQLEngine</span></span>|<span data-ttu-id="96945-228">Instala apenas o [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-228">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="96945-229">/FEATURES=SQLEngine,FullText</span><span class="sxs-lookup"><span data-stu-id="96945-229">/FEATURES=SQLEngine,FullText</span></span>|<span data-ttu-id="96945-230">Instala o [!INCLUDE[ssDE](../../includes/ssde-md.md)] e o texto completo.</span><span class="sxs-lookup"><span data-stu-id="96945-230">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and full-text.</span></span>|  
|<span data-ttu-id="96945-231">/FEATURES=SQLEngine,Conn</span><span class="sxs-lookup"><span data-stu-id="96945-231">/FEATURES=SQLEngine,Conn</span></span>|<span data-ttu-id="96945-232">Instala o [!INCLUDE[ssDE](../../includes/ssde-md.md)] e os componentes de conectividade.</span><span class="sxs-lookup"><span data-stu-id="96945-232">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the connectivity components.</span></span>|  
|<span data-ttu-id="96945-233">/FEATURES=SQLEngine,AS,IS,Conn</span><span class="sxs-lookup"><span data-stu-id="96945-233">/FEATURES=SQLEngine,AS,IS,Conn</span></span>|<span data-ttu-id="96945-234">Instala o [!INCLUDE[ssDE](../../includes/ssde-md.md)], o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]e os componentes de conectividade.</span><span class="sxs-lookup"><span data-stu-id="96945-234">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and the connectivity components.</span></span>|  
  
### <a name="installation-options"></a><span data-ttu-id="96945-235">Opções de instalação</span><span class="sxs-lookup"><span data-stu-id="96945-235">Installation Options</span></span>  
 <span data-ttu-id="96945-236">A Instalação dá suporte às opções de instalação a seguir enquanto instala o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] em um sistema operacional do Server Core:</span><span class="sxs-lookup"><span data-stu-id="96945-236">The Setup supports the following installation options while installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core operating system:</span></span>  
  
1.  <span data-ttu-id="96945-237">**Instalação da linha de comando**</span><span class="sxs-lookup"><span data-stu-id="96945-237">**Installation from Command Line**</span></span>  
  
     <span data-ttu-id="96945-238">Para instalar recursos específicos usando a opção de instalação do prompt de comando, use o parâmetro /FEATURES e especifique o recurso pai ou os valores de recursos listados.</span><span class="sxs-lookup"><span data-stu-id="96945-238">To install specific features using the command prompt installation option, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="96945-239">Um exemplo de como usar os parâmetros a partir da linha de comando é apresentado a seguir:</span><span class="sxs-lookup"><span data-stu-id="96945-239">The following is an example of using the parameters from the command line:</span></span>  
  
    ```cmd
    setup.exe /qs /ACTION=Install /FEATURES=SQLEngine,Replication /INSTANCENAME=MSSQLSERVER /SQLSVCACCOUNT="<DomainName\UserName>" /SQLSVCPASSWORD="<StrongPassword>" /SQLSYSADMINACCOUNTS="<DomainName\UserName>" /AGTSVCACCOUNT="NT AUTHORITY\Network Service" /TCPENABLED=1 /IACCEPTSQLSERVERLICENSETERMS  
    ```  
  
2.  <span data-ttu-id="96945-240">**Instalação usando o arquivo de configuração**</span><span class="sxs-lookup"><span data-stu-id="96945-240">**Installation using Configuration File**</span></span>  
  
     <span data-ttu-id="96945-241">A Instalação dá suporte ao uso do arquivo de configuração apenas através do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="96945-241">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="96945-242">O arquivo de configuração é um arquivo de texto com a estrutura básica de um parâmetro (par de nome/valor) e um comentário descritivo.</span><span class="sxs-lookup"><span data-stu-id="96945-242">The configuration file is a text file with the basic structure of a parameter (name/value pair) and a descriptive comment.</span></span> <span data-ttu-id="96945-243">O arquivo de configuração especificado no prompt de comando deve ter uma extensão de nome de arquivo .INI.</span><span class="sxs-lookup"><span data-stu-id="96945-243">The configuration file specified at the command prompt should have an .INI file name extension.</span></span> <span data-ttu-id="96945-244">Veja a seguir exemplos de ConfigurationFile.INI:</span><span class="sxs-lookup"><span data-stu-id="96945-244">See the following examples of ConfigurationFile.INI:</span></span>  
  
    -   <span data-ttu-id="96945-245">Instalando o [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96945-245">Installing [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
         <span data-ttu-id="96945-246">O exemplo a seguir mostra como instalar uma nova instância autônoma que inclui o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="96945-246">The following example shows how to install a new stand-alone instance that includes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)]:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine, and Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Accept the License agreement to continue with Installation  
  
        IAcceptSQLServerLicenseTerms="True"
        ```  
  
    -   <span data-ttu-id="96945-247">Instalando componentes de conectividade</span><span class="sxs-lookup"><span data-stu-id="96945-247">Installing connectivity components</span></span>  
  
         <span data-ttu-id="96945-248">O exemplo a seguir mostra como instalar os componentes de conectividade:</span><span class="sxs-lookup"><span data-stu-id="96945-248">The following example shows how to install the connectivity components:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=Conn  
  
        ; Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True
        ```  
  
    -   <span data-ttu-id="96945-249">Instalando todos os recursos com suporte</span><span class="sxs-lookup"><span data-stu-id="96945-249">Installing all supported features</span></span>  
  
         <span data-ttu-id="96945-250">O exemplo a seguir mostra como instalar todos os recursos com suporte do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] no Server Core:</span><span class="sxs-lookup"><span data-stu-id="96945-250">The following example shows how to install all supported features of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE,FullText,Replication,AS,IS,Conn  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine (SQL), or Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; The name of the account that the Analysis Services service runs under.   
  
        ASSVCACCOUNT= "NT Service\MSSQLServerOLAPService"  
  
        ; Specifies the list of administrator accounts that need to be provisioned.   
  
        ASSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Specifies the server mode of the Analysis Services instance. Valid values are MULTIDIMENSIONAL, POWERPIVOT or TABULAR. ASSERVERMODE is case-sensitive. All values must be expressed in upper case.   
  
        ASSERVERMODE="MULTIDIMENSIONAL"  
  
        ; Optional value, which specifies the state of the TCP protocol for the ssNoVersion service. Supported values are: 0 to disable the TCP protocol, and 1 to enable the TCP protocol.  
  
        TCPENABLED=1  
  
        ;Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True"  
        ```  
  
     <span data-ttu-id="96945-251">Os exemplos a seguir mostram como você pode iniciar a Instalação usando um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="96945-251">The following examples show how you can launch the Setup using a configuration file.</span></span>  
  
    -   <span data-ttu-id="96945-252">Arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="96945-252">Configuration file</span></span>  
  
         <span data-ttu-id="96945-253">Os exemplos a seguir mostram como usar o arquivo de configuração:</span><span class="sxs-lookup"><span data-stu-id="96945-253">Following are some examples of how to use the configuration file:</span></span>  
  
        -   <span data-ttu-id="96945-254">Para especificar o arquivo de configuração no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="96945-254">To specify the configuration file at the command prompt:</span></span>  
  
        ```cmd
        setup.exe /QS /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
        -   <span data-ttu-id="96945-255">Para especificar senhas no prompt de comando em vez de no arquivo de configuração:</span><span class="sxs-lookup"><span data-stu-id="96945-255">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
        ```cmd
        setup.exe /QS /SQLSVCPASSWORD="************" /ASSVCPASSWORD="************"  /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
    -   <span data-ttu-id="96945-256">DefaultSetup.ini</span><span class="sxs-lookup"><span data-stu-id="96945-256">DefaultSetup.ini</span></span>  
  
         <span data-ttu-id="96945-257">Se o arquivo DefaultSetup.ini estiver nas pastas \x86 e \x64 no nível raiz da mídia de origem do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , abra o arquivo DefaultSetup.ini e adicione o parâmetro *Features* a ele.</span><span class="sxs-lookup"><span data-stu-id="96945-257">If you have the DefaultSetup.ini file in the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media, open the DefaultSetup.ini file, and then add the *Features* parameter to the file.</span></span>  
  
         <span data-ttu-id="96945-258">Se o arquivo DefaultSetup.ini não existir, você poderá criá-lo e copiá-lo nas pastas \x86 e \x64 no nível raiz da mídia de origem do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96945-258">If the DefaultSetup.ini file does not exist, you can create it and copy it to the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media.</span></span>  
  
## <a name="configuring-remote-access-of-ssnoversion-running-on-server-core"></a><span data-ttu-id="96945-259">Configurando o acesso remoto do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em execução no Server Core</span><span class="sxs-lookup"><span data-stu-id="96945-259">Configuring Remote Access of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Running on Server Core</span></span>  
 <span data-ttu-id="96945-260">Execute as ações descritas abaixo para configurar o acesso remoto de uma instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] em execução em uma instalação do Server Core do [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-260">Perform the actions described below to configure remote access of a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance that is running on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
### <a name="enable-remote-connections-on-the-instance-of-ssnoversion"></a><span data-ttu-id="96945-261">Habilitar conexões remotas na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96945-261">Enable remote connections on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="96945-262">Para habilitar conexões remotas, use o SQLCMD.exe localmente e execute as instruções a seguir na instância do Server Core:</span><span class="sxs-lookup"><span data-stu-id="96945-262">To enable remote connections, use SQLCMD.exe locally and execute the following statements against the Server Core instance:</span></span>  
  
-   `EXEC sys.sp_configure N'remote access', N'1'`  
  
     `GO`  
  
-   `RECONFIGURE WITH OVERRIDE`  
  
     `GO`  
  
### <a name="enable-and-start-the-ssnoversion-browser-service"></a><span data-ttu-id="96945-263">Habilitar e iniciar o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span><span class="sxs-lookup"><span data-stu-id="96945-263">Enable and start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service</span></span>  
 <span data-ttu-id="96945-264">Por padrão, o serviço Navegador está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="96945-264">By default, the Browser service is disabled.</span></span>  <span data-ttu-id="96945-265">Se ele estiver desabilitado em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em execução no Server Core, execute o seguinte comando no prompt de comando para habilitá-lo:</span><span class="sxs-lookup"><span data-stu-id="96945-265">If it is disabled on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on Server Core, run the following command from the command prompt to enable it:</span></span>  
  
 `sc config SQLBROWSER start= auto`  
  
 <span data-ttu-id="96945-266">Depois de habilitá-lo, execute o seguinte comando a partir do prompt de comando para iniciar o serviço:</span><span class="sxs-lookup"><span data-stu-id="96945-266">After it is enabled, run the following command from the command prompt to start the service:</span></span>  
  
 `net start SQLBROWSER`  
  
### <a name="create-exceptions-in-windows-firewall"></a><span data-ttu-id="96945-267">Criar exceções no Firewall do Windows</span><span class="sxs-lookup"><span data-stu-id="96945-267">Create exceptions in Windows Firewall</span></span>  
 <span data-ttu-id="96945-268">Para criar exceções para o acesso do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no Firewall do Windows, siga as etapas especificadas em [Configurar o Firewall do Windows para permitir acesso ao SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="96945-268">To create exceptions for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access in Windows Firewall, follow the steps specified in [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
### <a name="enable-tcpip-on-the-instance-of-ssnoversion"></a><span data-ttu-id="96945-269">Habilitar TCP/IP na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96945-269">Enable TCP/IP on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="96945-270">O protocolo TCP/IP pode ser habilitado por meio do Windows PowerShell para uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no Server Core.</span><span class="sxs-lookup"><span data-stu-id="96945-270">The TCP/IP protocol can be enabled through Windows PowerShell for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on Server Core.</span></span> <span data-ttu-id="96945-271">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="96945-271">Follow these steps:</span></span>  
  
1.  <span data-ttu-id="96945-272">No computador executando o [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, inicie o Gerenciador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="96945-272">On the computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, launch Task Manager.</span></span>  
  
2.  <span data-ttu-id="96945-273">Na guia **Aplicativos** , clique em **Nova Tarefa**.</span><span class="sxs-lookup"><span data-stu-id="96945-273">On the **Applications** tab, click **New Task**.</span></span>  
  
3.  <span data-ttu-id="96945-274">Na caixa de diálogo **Criar Nova Tarefa** , digite **sqlps.exe** no campo **Abrir** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="96945-274">In the **Create New Task** dialog box, type **sqlps.exe** in the **Open** field and then click **OK**.</span></span> <span data-ttu-id="96945-275">Isso abre a janela do \*\* [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell\*\* .</span><span class="sxs-lookup"><span data-stu-id="96945-275">This opens the **[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window.</span></span>  
  
4.  <span data-ttu-id="96945-276">Na janela **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell**, execute o script a seguir para habilitar o protocolo TCP/IP:</span><span class="sxs-lookup"><span data-stu-id="96945-276">In the **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window, run the following script to enable the TCP/IP protocol:</span></span>  
  
```powershell
$smo = 'Microsoft.SqlServer.Management.Smo.'  
$wmi = New-Object ($smo + 'Wmi.ManagedComputer')  
# Enable the TCP protocol on the default instance.  If the instance is named, replace MSSQLSERVER with the instance name in the following line.  
$uri = "ManagedComputer[@Name='" + (get-item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
$Tcp = $wmi.GetSmoObject($uri)  
$Tcp.IsEnabled = $true  
$Tcp.Alter()  
$Tcp  
```  
  
## <a name="uninstallation"></a><span data-ttu-id="96945-277">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="96945-277">Uninstallation</span></span>  
 <span data-ttu-id="96945-278">Depois que fizer logon em um computador executando o [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, você terá um ambiente de desktop limitado com um prompt de comando de Administrador.</span><span class="sxs-lookup"><span data-stu-id="96945-278">After you log on to a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, you have a limited desktop environment with an Administrator command prompt.</span></span> <span data-ttu-id="96945-279">Você pode usar esse prompt de comando para iniciar a desinstalação de uma instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-279">You can use this command prompt to initiate uninstallation of an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="96945-280">Para desinstalar uma instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], inicie a desinstalação do prompt de comando no modo silencioso completo usando o parâmetro /Q ou no modo silencioso simples usando o parâmetro /QS.</span><span class="sxs-lookup"><span data-stu-id="96945-280">To uninstall an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], launch the uninstallation from the command prompt in full quiet mode by using the /Q parameter, or quiet simple mode by using the /QS parameter.</span></span> <span data-ttu-id="96945-281">O parâmetro /QS mostra o progresso por meio da interface de usuário, mas não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="96945-281">The /QS parameter shows progress through the UI, but does not accept any input.</span></span> <span data-ttu-id="96945-282">/Q é executado no modo silencioso sem nenhuma interface de usuário.</span><span class="sxs-lookup"><span data-stu-id="96945-282">/Q runs in a quiet mode without any user interface.</span></span>  
  
 <span data-ttu-id="96945-283">Para desinstalar uma instância existente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="96945-283">To uninstall an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```cmd
setup.exe /Q /Action=Uninstall /FEATURES=SQLEngine,AS,IS /INSTANCENAME=MSSQLSERVER  
```  
  
 <span data-ttu-id="96945-284">Para remover uma instância nomeada, especifique o nome da instância, em vez de "MSSQLSERVER" no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="96945-284">To remove a named instance, specify the name of the instance instead of "MSSQLSERVER" in the preceding example.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="96945-285">Se você fechar acidentalmente o prompt de comando, siga estas etapas para iniciar um novo prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="96945-285">If you accidentally close the command prompt, you can start a new command prompt by following these steps:</span></span>  
> 
>  1.  <span data-ttu-id="96945-286">Pressione Ctrl+Shift+Esc para exibir o Gerenciador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="96945-286">Press Ctrl+Shift+Esc to display Task Manager.</span></span>  
> 2.  <span data-ttu-id="96945-287">Na guia **Aplicativos** , clique em **Nova Tarefa**.</span><span class="sxs-lookup"><span data-stu-id="96945-287">On the **Applications** tab, click **New Task**.</span></span>  
> 3.  <span data-ttu-id="96945-288">Na caixa de diálogo **Criar Nova Tarefa** , digite **cmd** no campo **Abrir** e [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96945-288">In the **Create New Task** dialog box, type **cmd** in the **Open** field and then [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96945-289">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96945-289">See Also</span></span>  
 <span data-ttu-id="96945-290">[Instalar o SQL Server 2014 usando um arquivo de configuração](install-sql-server-using-a-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="96945-290">[Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md) </span></span>  
 <span data-ttu-id="96945-291">[Instalar o SQL Server 2014 no prompt de comando](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="96945-291">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="96945-292">[Recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="96945-292">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="96945-293">[Guia de Introdução da opção de instalação do Server Core](https://go.microsoft.com/fwlink/?LinkId=221422) </span><span class="sxs-lookup"><span data-stu-id="96945-293">[Server Core Installation Option Getting Started Guide](https://go.microsoft.com/fwlink/?LinkId=221422) </span></span>  
 <span data-ttu-id="96945-294">[Configurando uma instalação do Server Core: visão geral](https://go.microsoft.com/fwlink/?LinkId=221423) </span><span class="sxs-lookup"><span data-stu-id="96945-294">[Configuring a Server Core installation: Overview](https://go.microsoft.com/fwlink/?LinkId=221423) </span></span>  
 <span data-ttu-id="96945-295">[Cmdlets de cluster de failover no Windows PowerShell listados por foco de tarefa](https://go.microsoft.com/fwlink/?LinkId=221419) </span><span class="sxs-lookup"><span data-stu-id="96945-295">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://go.microsoft.com/fwlink/?LinkId=221419) </span></span>  
 [<span data-ttu-id="96945-296">Mapeamento de comandos do Cluster.exe para cmdlets do Windows PowerShell para clusters de failover</span><span class="sxs-lookup"><span data-stu-id="96945-296">Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters</span></span>](https://go.microsoft.com/fwlink/?LinkId=221421)  
