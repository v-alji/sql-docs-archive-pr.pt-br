---
title: Implantar soluções do PowerPivot no SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f202a2b7-34e0-43aa-90d5-c9a085a37c32
author: minewiskan
ms.author: owend
ms.openlocfilehash: 043647988598f932b70cc06e6bb5492d66864372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576016"
---
# <a name="deploy-powerpivot-solutions-to-sharepoint"></a><span data-ttu-id="e3e22-102">Implantar soluções PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="e3e22-102">Deploy PowerPivot Solutions to SharePoint</span></span>
  <span data-ttu-id="e3e22-103">Use as instruções a seguir para implantar manualmente dois pacotes de solução que adicionam recursos do PowerPivot a um ambiente do SharePoint Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e3e22-103">Use the following instructions to manually deploy two solution packages that add PowerPivot features to a SharePoint Server 2010 environment.</span></span> <span data-ttu-id="e3e22-104">Implantar as soluções é uma etapa necessária para configurar o PowerPivot para SharePoint em um servidor do SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="e3e22-104">Deploying the solutions is a required step for configuring PowerPivot for SharePoint on a SharePoint 2010 server.</span></span> <span data-ttu-id="e3e22-105">Para exibir a lista completa de etapas necessárias, consulte [Administração e configuração do servidor PowerPivot na administração central](power-pivot-server-administration-and-configuration-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="e3e22-105">To view the complete list of required steps, see [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md).</span></span>  
  
 <span data-ttu-id="e3e22-106">Como alternativa, você pode usar a Ferramenta de Configuração do PowerPivot para implantar as soluções.</span><span class="sxs-lookup"><span data-stu-id="e3e22-106">Alternatively, you can use the PowerPivot Configuration Tool to deploy the solutions.</span></span> <span data-ttu-id="e3e22-107">Usar a ferramenta de configuração é mais fácil e mais eficiente para uma única instalação de servidor, mas você pode querer usar a Administração Central e o PowerShell se preferir usar uma ferramenta familiar ou se estiver configurando vários recursos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="e3e22-107">Using the configuration tool is easier and more efficient for a single server installation, but you might want to use Central Administration and PowerShell if you prefer using a familiar tool or if you are configuring multiple features at the same time.</span></span> <span data-ttu-id="e3e22-108">Para obter mais informações sobre como usar a ferramenta de configuração, consulte [PowerPivot ferramentas de configuração](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e3e22-108">For more information about using the configuration tool, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
 <span data-ttu-id="e3e22-109">Antes de implantar as soluções, você deverá primeiro instalar o PowerPivot para SharePoint usando a mídia de instalação do SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="e3e22-109">Before deploying the solutions, you must first install PowerPivot for SharePoint using the SQL Server 2012 installation media.</span></span> <span data-ttu-id="e3e22-110">A instalação do SQL Server instala os pacotes de solução que você está prestes a implantar.</span><span class="sxs-lookup"><span data-stu-id="e3e22-110">SQL Server Setup installs the solution packages that you are about to deploy.</span></span>  
  
 <span data-ttu-id="e3e22-111">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="e3e22-111">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="e3e22-112">Pré-requisito: Verifique se o aplicativo Web usa a autenticação de modo clássico</span><span class="sxs-lookup"><span data-stu-id="e3e22-112">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>](#bkmk_classic)  
  
 [<span data-ttu-id="e3e22-113">Etapa 1: implantar a solução de farm</span><span class="sxs-lookup"><span data-stu-id="e3e22-113">Step 1: Deploy the Farm Solution</span></span>](#bkmk_farm)  
  
 [<span data-ttu-id="e3e22-114">Etapa 2: implantar a solução de aplicativo Web do PowerPivot na Administração Central</span><span class="sxs-lookup"><span data-stu-id="e3e22-114">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>](#deployCA)  
  
 [<span data-ttu-id="e3e22-115">Etapa 3: implantar a solução de aplicativo Web do PowerPivot em outros aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="e3e22-115">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>](#deployUI)  
  
 [<span data-ttu-id="e3e22-116">Reimplantar ou cancelar a solução</span><span class="sxs-lookup"><span data-stu-id="e3e22-116">Redeploy or retract the Solution</span></span>](#retract)  
  
 [<span data-ttu-id="e3e22-117">Sobre as soluções PowerPivot</span><span class="sxs-lookup"><span data-stu-id="e3e22-117">About the PowerPivot Solutions</span></span>](#intro)  
  
##  <a name="prerequisite-verify-the-web-application-uses-classic-mode-authentication"></a><a name="bkmk_classic"></a> <span data-ttu-id="e3e22-118">Pré-requisito: verificar se o aplicativo Web usa a autenticação de modo clássico</span><span class="sxs-lookup"><span data-stu-id="e3e22-118">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>  
 <span data-ttu-id="e3e22-119">O PowerPivot para SharePoint tem suporte apenas para aplicativos Web que utilizam a autenticação de modo clássico do Windows.</span><span class="sxs-lookup"><span data-stu-id="e3e22-119">PowerPivot for SharePoint is only supported for web applications that use Windows-classic mode authentication.</span></span> <span data-ttu-id="e3e22-120">Para verificar se o aplicativo usa o modo clássico, execute o seguinte cmdlet do PowerShell no **Shell de gerenciamento do sharepoint 2010**, substituindo `http://<top-level site name>` pelo nome do seu site do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e3e22-120">To check whether the application uses Classic mode, run the following PowerShell cmdlet from the **SharePoint 2010 Management Shell**, replacing `http://<top-level site name>` with the name of your SharePoint site:</span></span>  
  
```powershell
Get-SPWebApplication http://<top-level site name> | Format-List UseClaimsAuthentication  
```  
  
 <span data-ttu-id="e3e22-121">O valor retornado deve ser **false**.</span><span class="sxs-lookup"><span data-stu-id="e3e22-121">The return value should be **false**.</span></span> <span data-ttu-id="e3e22-122">Se for **true**, você não poderá acessar dados PowerPivot com este aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="e3e22-122">If it is **true**, you cannot access PowerPivot data with this web application.</span></span>  
  
##  <a name="step-1-deploy-the-farm-solution"></a><a name="bkmk_farm"></a><span data-ttu-id="e3e22-123">Etapa 1: implantar a solução de farm</span><span class="sxs-lookup"><span data-stu-id="e3e22-123">Step 1: Deploy the Farm Solution</span></span>  
 <span data-ttu-id="e3e22-124">Esta seção mostra como implantar soluções usando o PowerShell, mas você também pode usar a Ferramenta de Configuração do PowerPivot para concluir esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="e3e22-124">This section shows you how to deploy solutions using PowerShell, but you can also use the PowerPivot Configuration Tool to complete this task.</span></span> <span data-ttu-id="e3e22-125">Para obter mais informações, consulte [Configurar ou reparar 2010 PowerPivot para SharePoint &#40;ferramenta de configuração do PowerPivot&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="e3e22-125">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="e3e22-126">Esta tarefa somente precisa ser executada uma vez, depois de instalar o PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3e22-126">This task only needs to be performed once, after you install PowerPivot for SharePoint.</span></span>  
  
1.  <span data-ttu-id="e3e22-127">Em um servidor que tenha uma instalação do PowerPivot para SharePoint, abra um shell de gerenciamento do SharePoint 2010 usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="e3e22-127">On a server that has an installation of PowerPivot for SharePoint, open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="e3e22-128">Execute o cmdlet a seguir para adicionar a solução do farm.</span><span class="sxs-lookup"><span data-stu-id="e3e22-128">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="e3e22-129">O cmdlet retorna o nome da solução, sua ID de solução e Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="e3e22-129">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="e3e22-130">Na próxima etapa, você implantará a solução.</span><span class="sxs-lookup"><span data-stu-id="e3e22-130">In the next step, you will deploy the solution.</span></span>  
  
3.  <span data-ttu-id="e3e22-131">Execute o cmdlet seguinte para implantar a solução do farm:</span><span class="sxs-lookup"><span data-stu-id="e3e22-131">Run the next cmdlet to deploy the farm solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
##  <a name="step-2-deploy-the-powerpivot-web-application-solution-to-central-administration"></a><a name="deployCA"></a><span data-ttu-id="e3e22-132">Etapa 2: implantar a solução de aplicativo Web PowerPivot na administração central</span><span class="sxs-lookup"><span data-stu-id="e3e22-132">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>  
 <span data-ttu-id="e3e22-133">Depois de implantar a solução do farm, você deverá implantar a solução de aplicativo Web na Administração Central.</span><span class="sxs-lookup"><span data-stu-id="e3e22-133">After you deploy the farm solution, you must deploy the Web application solution to Central Administration.</span></span> <span data-ttu-id="e3e22-134">Essa etapa adiciona o Painel de Gerenciamento do PowerPivot à Administração Central.</span><span class="sxs-lookup"><span data-stu-id="e3e22-134">This step adds the PowerPivot Management Dashboard to Central Administration.</span></span>  
  
1.  <span data-ttu-id="e3e22-135">Abra um Shell de Gerenciamento do SharePoint 2010 usando a opção **Executar como Administrador** .</span><span class="sxs-lookup"><span data-stu-id="e3e22-135">Open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="e3e22-136">Execute o cmdlet a seguir para criar uma referência à Administração Central:</span><span class="sxs-lookup"><span data-stu-id="e3e22-136">Run the following cmdlet to create a reference to Central Administration:</span></span>  
  
    ```powershell
    $centralAdmin = $(Get-SPWebApplication -IncludeCentralAdministration | Where { $_.IsAdministrationWebApplication -eq $TRUE})  
    ```  
  
3.  <span data-ttu-id="e3e22-137">Execute o cmdlet a seguir para adicionar a solução do farm.</span><span class="sxs-lookup"><span data-stu-id="e3e22-137">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotWebApp.wsp"  
    ```  
  
     <span data-ttu-id="e3e22-138">O cmdlet retorna o nome da solução, sua ID de solução e Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="e3e22-138">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="e3e22-139">Na próxima etapa, você implantará a solução.</span><span class="sxs-lookup"><span data-stu-id="e3e22-139">In the next step, you will deploy the solution.</span></span>  
  
4.  <span data-ttu-id="e3e22-140">Execute o cmdlet seguinte para instalar a solução de aplicativo Web na Administração Central.</span><span class="sxs-lookup"><span data-stu-id="e3e22-140">Run the next cmdlet to install the web application solution to Central Administration.</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotWebApp.wsp -GACDeployment -Force -WebApplication $centralAdmin  
    ```  
  
 <span data-ttu-id="e3e22-141">Agora que a solução de aplicativo Web está implantada na Administração Central, você poderá usar a Administração Central para concluir todas as etapas de configuração restantes.</span><span class="sxs-lookup"><span data-stu-id="e3e22-141">Now that the web application solution is deployed to Central Administration, you can use Central Administration to complete all remaining configuration steps.</span></span>  
  
##  <a name="step-3-deploy-the-powerpivot-web-application-solution-to-other-web-applications"></a><a name="deployUI"></a><span data-ttu-id="e3e22-142">Etapa 3: implantar a solução de aplicativo Web PowerPivot em outros aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="e3e22-142">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>  
 <span data-ttu-id="e3e22-143">Na tarefa anterior, você implantou o Powerpivotwebapp.wsp na Administração Central.</span><span class="sxs-lookup"><span data-stu-id="e3e22-143">In the previous task, you deployed Powerpivotwebapp.wsp to Central Administration.</span></span> <span data-ttu-id="e3e22-144">Nesta seção, você implanta o powerpivotwebapp.wsp em cada aplicativo Web existente que dá suporte a acesso a dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e3e22-144">In this section, you deploy the powerpivotwebapp.wsp on each existing web application that supports PowerPivot data access.</span></span> <span data-ttu-id="e3e22-145">Se você adicionar mais aplicativos Web posteriormente, repita esta etapa para esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e3e22-145">If you add more web applications later, be sure to repeat this step for those additional web applications.</span></span>  
  
1.  <span data-ttu-id="e3e22-146">Na Administração Central, em Configurações do Sistema, clique em **Gerenciar soluções de farm**.</span><span class="sxs-lookup"><span data-stu-id="e3e22-146">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="e3e22-147">Clique em **powerpivotwebapp. wsp**.</span><span class="sxs-lookup"><span data-stu-id="e3e22-147">Click **powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="e3e22-148">Clique em **Implantar Solução**.</span><span class="sxs-lookup"><span data-stu-id="e3e22-148">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="e3e22-149">Em **implantar em?**, selecione o aplicativo Web do SharePoint para o qual você deseja adicionar suporte ao recurso do PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e3e22-149">In **Deploy To?**, select the SharePoint web application for which you want to add PowerPivot feature support.</span></span>  
  
5.  <span data-ttu-id="e3e22-150">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3e22-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="e3e22-151">Repita para outros aplicativos Web do SharePoint que também oferecerão suporte ao acesso a dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e3e22-151">Repeat for other SharePoint web applications that will also support PowerPivot data access.</span></span>  
  
##  <a name="redeploy-or-retract-the-solution"></a><a name="retract"></a><span data-ttu-id="e3e22-152">Reimplantar ou cancelar a solução</span><span class="sxs-lookup"><span data-stu-id="e3e22-152">Redeploy or retract the Solution</span></span>  
 <span data-ttu-id="e3e22-153">Embora a Administração Central do SharePoint forneça o cancelamento da solução, você não precisa cancelar o arquivo powerpivotwebapp.wsp, a menos que esteja solucionando problemas sistematicamente de uma instalação ou um problema de implantação do patch.</span><span class="sxs-lookup"><span data-stu-id="e3e22-153">Although SharePoint Central Administration provides solution retraction, you do not need to retract the powerpivotwebapp.wsp file unless you are systematically troubleshooting an installation or patch deployment problem.</span></span>  
  
1.  <span data-ttu-id="e3e22-154">Na Administração Central do SharePoint 2010, em Configurações do Sistema, clique em **Gerenciar soluções de farm**.</span><span class="sxs-lookup"><span data-stu-id="e3e22-154">In SharePoint 2010 Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="e3e22-155">Clique em **Powerpivotwebapp.wsp**.</span><span class="sxs-lookup"><span data-stu-id="e3e22-155">Click **Powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="e3e22-156">Clique em **Cancelar Solução**.</span><span class="sxs-lookup"><span data-stu-id="e3e22-156">Click **Retract Solution**.</span></span>  
  
 <span data-ttu-id="e3e22-157">Se você encontrar problemas de implantação de servidor que você rastreie de volta para a solução de farm, você pode reimplantá-lo executando a opção de **reparo** na ferramenta de configuração do PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e3e22-157">If you encounter server deployment issues that you trace back to the farm solution, you can redeploy it by running the **Repair** option in the PowerPivot Configuration Tool.</span></span> <span data-ttu-id="e3e22-158">As operações de reparo pela ferramenta são preferíveis porque exigem menos etapas de sua parte.</span><span class="sxs-lookup"><span data-stu-id="e3e22-158">Repair operations via the tool is preferred because it requires fewer steps on your part.</span></span> <span data-ttu-id="e3e22-159">Para obter mais informações, consulte [Configurar ou reparar 2010 PowerPivot para SharePoint &#40;ferramenta de configuração do PowerPivot&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="e3e22-159">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="e3e22-160">Se você ainda desejar reimplantar todas as soluções, siga esta ordem:</span><span class="sxs-lookup"><span data-stu-id="e3e22-160">If you still want to re-deploy all solutions, be sure to do so in this order:</span></span>  
  
1.  <span data-ttu-id="e3e22-161">Cancele a solução de aplicativo Web PowerPivot de todos os aplicativos Web do SharePoint que o utilizam.</span><span class="sxs-lookup"><span data-stu-id="e3e22-161">Retract the PowerPivot Web application solution from all SharePoint web applications that use it.</span></span>  
  
2.  <span data-ttu-id="e3e22-162">Cancele a solução de farm PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e3e22-162">Retract the PowerPivot farm solution.</span></span>  
  
3.  <span data-ttu-id="e3e22-163">Reimplante a solução de farm PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e3e22-163">Redeploy the PowerPivot farm solution.</span></span>  
  
4.  <span data-ttu-id="e3e22-164">Reimplante a solução de aplicativo Web PowerPivot para todos os aplicativos Web do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3e22-164">Redeploy the PowerPivot Web application solution to all SharePoint web applications.</span></span>  
  
##  <a name="about-the-powerpivot-solutions"></a><a name="intro"></a><span data-ttu-id="e3e22-165">Sobre as soluções PowerPivot</span><span class="sxs-lookup"><span data-stu-id="e3e22-165">About the PowerPivot Solutions</span></span>  
 <span data-ttu-id="e3e22-166">O PowerPivot para SharePoint usa dois pacotes de soluções para implantar páginas de aplicativos e arquivos de programas no farm e em aplicativos Web individuais.</span><span class="sxs-lookup"><span data-stu-id="e3e22-166">PowerPivot for SharePoint uses two solution packages to deploy its application pages and program files to the farm and to individual web applications.</span></span>  
  
-   <span data-ttu-id="e3e22-167">A solução de farm é global.</span><span class="sxs-lookup"><span data-stu-id="e3e22-167">The farm solution is global.</span></span> <span data-ttu-id="e3e22-168">É implantada uma vez e permanece disponível automaticamente para qualquer servidor novo do PowerPivot para SharePoint adicionado ao farm posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e3e22-168">It is deployed once and then becomes automatically available to any new PowerPivot for SharePoint servers that you add to the farm later.</span></span>  
  
-   <span data-ttu-id="e3e22-169">A solução de aplicativo Web é específica do aplicativo e deve ser implantada em cada aplicativo Web no farm, inclusive o aplicativo Web Administração Central.</span><span class="sxs-lookup"><span data-stu-id="e3e22-169">The web application solution is application-specific and must be deployed to each web application in the farm, including the Central Administration web application.</span></span>  
  
 <span data-ttu-id="e3e22-170">Cada solução é implantada de maneira diferente.</span><span class="sxs-lookup"><span data-stu-id="e3e22-170">Each solution is deployed differently.</span></span>  <span data-ttu-id="e3e22-171">A solução do farm é implantada uma vez, depois que a primeira instância do PowerPivot para SharePoint é instalada.</span><span class="sxs-lookup"><span data-stu-id="e3e22-171">The farm solution is deployed once, after the first PowerPivot for SharePoint instance is installed.</span></span> <span data-ttu-id="e3e22-172">Para implantar a solução do farm, use a Ferramenta de Configuração do PowerPivot ou os cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3e22-172">To deploy the farm solution, you use the PowerPivot Configuration Tool or PowerShell cmdlets.</span></span>  
  
 <span data-ttu-id="e3e22-173">A solução do aplicativo Web é implantada inicialmente na Administração Central, seguida por implantações subsequentes da solução em qualquer aplicativo Web adicional que dará suporte a solicitações para dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e3e22-173">The web application solution is initially deployed to Central Administration, followed by subsequent solution deployments to any additional web applications that will support requests for PowerPivot data.</span></span> <span data-ttu-id="e3e22-174">Para implantar a solução de aplicativo Web da Administração Central, você deve usar a Ferramenta de Configuração do PowerPivot ou cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3e22-174">To deploy the web application solution to Central Administration, you must use the PowerPivot Configuration Tool or PowerShell cmdlet.</span></span> <span data-ttu-id="e3e22-175">Para todos os outros aplicativos Web, você pode implantar a solução de aplicativo Web manualmente usando a Administração Central ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3e22-175">For all other web applications, you can deploy the web application solution manually using Central Administration or PowerShell.</span></span>  
  
|<span data-ttu-id="e3e22-176">Solução</span><span class="sxs-lookup"><span data-stu-id="e3e22-176">Solution</span></span>|<span data-ttu-id="e3e22-177">Descrição</span><span class="sxs-lookup"><span data-stu-id="e3e22-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e3e22-178">Powerpivotfarm.wsp</span><span class="sxs-lookup"><span data-stu-id="e3e22-178">Powerpivotfarm.wsp</span></span>|<span data-ttu-id="e3e22-179">Adiciona o Microsoft.AnalysisServices.SharePoint.Integration.dll ao assembly global.</span><span class="sxs-lookup"><span data-stu-id="e3e22-179">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="e3e22-180">Adiciona o Microsoft.AnalysisServices.ChannelTransport.dll ao assembly global.</span><span class="sxs-lookup"><span data-stu-id="e3e22-180">Adds Microsoft.AnalysisServices.ChannelTransport.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="e3e22-181">Instala recursos e arquivos de recurso e registra tipos de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e3e22-181">Installs features and resources files, and registers content types.</span></span><br /><br /> <span data-ttu-id="e3e22-182">Adiciona modelos de biblioteca para bibliotecas da Galeria PowerPivot e do Feed de Dados.</span><span class="sxs-lookup"><span data-stu-id="e3e22-182">Adds library templates for PowerPivot Gallery and Data Feed libraries.</span></span><br /><br /> <span data-ttu-id="e3e22-183">Adiciona páginas de aplicativos para configuração de aplicativos de serviço, Painel de Gerenciamento PowerPivot, atualização de dados e Galeria PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e3e22-183">Adds application pages for service application configuration, PowerPivot Management Dashboard, data refresh, and PowerPivot Gallery.</span></span>|  
|<span data-ttu-id="e3e22-184">Powerpivotwebapp.wsp</span><span class="sxs-lookup"><span data-stu-id="e3e22-184">Powerpivotwebapp.wsp</span></span>|<span data-ttu-id="e3e22-185">Adiciona arquivos de recursos Microsoft.AnalysisServices.SharePoint.Integration.dll à pasta de extensões no servidor Web front-end.</span><span class="sxs-lookup"><span data-stu-id="e3e22-185">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll resources files to the web server extensions folder on the Web front-end.</span></span><br /><br /> <span data-ttu-id="e3e22-186">Adiciona serviço Web do PowerPivot ao front-end Web.</span><span class="sxs-lookup"><span data-stu-id="e3e22-186">Adds PowerPivot Web service to the Web-front end.</span></span><br /><br /> <span data-ttu-id="e3e22-187">Adiciona geração de imagens em miniatura para Galeria PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="e3e22-187">Adds thumbnail image generation for PowerPivot Gallery.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3e22-188">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3e22-188">See Also</span></span>  
 <span data-ttu-id="e3e22-189">[Atualizar PowerPivot para SharePoint](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="e3e22-189">[Upgrade PowerPivot for SharePoint](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="e3e22-190">[Administração e configuração do servidor PowerPivot na administração central](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="e3e22-190">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 [<span data-ttu-id="e3e22-191">Configuração do PowerPivot usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3e22-191">PowerPivot Configuration using Windows PowerShell</span></span>](power-pivot-configuration-using-windows-powershell.md)  
