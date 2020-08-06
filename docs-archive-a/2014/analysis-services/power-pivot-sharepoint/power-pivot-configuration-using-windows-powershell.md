---
title: Configuração do PowerPivot usando o Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4d83e53e-04f1-417d-9039-d9e81ae0483d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 83b42da3e676a291bb021c02ee52e9a810207397
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582146"
---
# <a name="powerpivot-configuration-using-windows-powershell"></a><span data-ttu-id="f606b-102">Configuração do PowerPivot usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f606b-102">PowerPivot Configuration using Windows PowerShell</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="f606b-103">inclui cmdlets do Windows PowerShell que você pode usar para configurar uma instalação do [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f606b-103">includes Windows PowerShell cmdlets that you can use to configure an installation of [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span></span> <span data-ttu-id="f606b-104">A configuração completa de uma instalação com o PowerShell exige o uso de cmdlets do SharePoint e do PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f606b-104">To fully configure an installation with PowerShell requires the use of both SharePoint cmdlets and PowerPivot for SharePoint cmdlets.</span></span> <span data-ttu-id="f606b-105">A maior parte da configuração pode ser concluída usando uma das ferramentas do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f606b-105">A majority of configuration can be completed using one of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] tools.</span></span> <span data-ttu-id="f606b-106">Para obter mais informações sobre as ferramentas, consulte [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f606b-106">For more information on the tools, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f606b-107">Para um farm do SharePoint 2010, o SharePoint 2010 SP1 deve ser instalado antes da configuração do PowerPivot para SharePoint ou de um farm do SharePoint que usa um servidor de banco de dados do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f606b-107">For a SharePoint 2010 farm, SharePoint 2010 SP1 must be installed before you can configure either PowerPivot for SharePoint, or a SharePoint farm that uses a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] database server.</span></span> <span data-ttu-id="f606b-108">Se você ainda não instalou o service pack; instale-o antes de começar a configurar o servidor.</span><span class="sxs-lookup"><span data-stu-id="f606b-108">If you have not yet installed the service pack, install it before you begin configuring the server.</span></span>  
  
## <a name="benefits-of-configuring-powerpivot-for-sharepoint-using-powershell"></a><span data-ttu-id="f606b-109">Benefícios da configuração do PowerPivot para SharePoint usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f606b-109">Benefits of Configuring PowerPivot for SharePoint Using PowerShell</span></span>  
 <span data-ttu-id="f606b-110">É possível criar arquivos de script do Windows PowerShell (.ps1) para automatizar tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="f606b-110">You can build Windows PowerShell script (.ps1) files to automate configuration tasks.</span></span> <span data-ttu-id="f606b-111">Essa abordagem será recomendada se você precisar de instalação e etapas de configuração controladas por script que possa ser executado em qualquer servidor.</span><span class="sxs-lookup"><span data-stu-id="f606b-111">This approach is recommended if you require scripted installation and configuration steps that you can run on any server.</span></span> <span data-ttu-id="f606b-112">Você pode precisar desse script como parte de um plano de recuperação de desastre para reconstruir um servidor no caso de um problema de hardware.</span><span class="sxs-lookup"><span data-stu-id="f606b-112">You might require such a script as part of a disaster recovery plan for rebuilding a server in the event of a hardware failure.</span></span>  
  
## <a name="view-a-list-of-the-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="f606b-113">Exibir uma lista de cmdlets do PowerPivot em um servidor</span><span class="sxs-lookup"><span data-stu-id="f606b-113">View a list of the PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="f606b-114">Para ver o conteúdo e exemplos dos [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cmdlets, consulte [referência do PowerShell para PowerPivot para SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span><span class="sxs-lookup"><span data-stu-id="f606b-114">To see content and examples of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cmdlets, see [PowerShell Reference for PowerPivot for SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span></span>  
  
 <span data-ttu-id="f606b-115">Para usar o PowerShell para exibir uma lista de cmdlets do PowerPivot:</span><span class="sxs-lookup"><span data-stu-id="f606b-115">To use PowerShell to view a list of the PowerPivot cmdlets:</span></span>  
  
1.  <span data-ttu-id="f606b-116">Abra um Shell de Gerenciamento do SharePoint usando a opção **Executar como Administrador** .</span><span class="sxs-lookup"><span data-stu-id="f606b-116">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="f606b-117">Digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f606b-117">Enter the following command:</span></span>  
  
    ```powershell
    Get-Help *powerpivot*  
    ```  
  
     <span data-ttu-id="f606b-118">Você deve ver uma lista de cmdlets que incluem PowerPivot no nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f606b-118">You should see a list of cmdlets that include PowerPivot in the cmdlet name.</span></span> <span data-ttu-id="f606b-119">Por exemplo, `Get-PowerPivotServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="f606b-119">For example `Get-PowerPivotServiceApplication`.</span></span> <span data-ttu-id="f606b-120">O número de cmdlets disponíveis depende da versão do Analysis Services que você está usando.</span><span class="sxs-lookup"><span data-stu-id="f606b-120">The number of cmdlets available depends on the version of Analysis Services you are using.</span></span>  
  
    -   <span data-ttu-id="f606b-121">10 cmdlets com o servidor SQL Server 2012 SP1 Analysis Services configurados no modo do SharePoint e com o SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="f606b-121">10 cmdlets with SQL Server 2012 SP1 Analysis Services server configured in SharePoint mode, and SharePoint 2013.</span></span> <span data-ttu-id="f606b-122">A versão 2012 SP1 utiliza uma nova arquitetura que permite ao Analysis Server ser executado fora do farm do SharePoint e exige menos cmdlets do Windows PowerShell de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f606b-122">The 2012 SP1 version utilizes a new architecture that allows the Analysis Server to run outside the SharePoint farm and requires fewer management Windows PowerShell cmdlets.</span></span>  
  
    -   <span data-ttu-id="f606b-123">17 cmdlets com o servidor SQL Server 2012 Analysis Services configurados no modo do SharePoint e com o SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="f606b-123">17 cmdlets with SQL Server 2012 Analysis Services server configured in SharePoint mode, and SharePoint 2010.</span></span>  
  
     <span data-ttu-id="f606b-124">Se nenhum comando for retornado na lista ou se você vir uma mensagem de erro semelhante a " `get-help could not find *powerpivot* in a help file in this session.` ", consulte a próxima seção neste tópico para obter instruções sobre como habilitar os cmdlets do PowerPivot no servidor.</span><span class="sxs-lookup"><span data-stu-id="f606b-124">If no commands are returned in the list or you see an error message similar to "`get-help could not find *powerpivot* in a help file in this session.`", see the next section in this topic for instructions on how to enable the PowerPivot cmdlets on the server.</span></span>  
  
     <span data-ttu-id="f606b-125">Todos os cmdlets têm ajuda online.</span><span class="sxs-lookup"><span data-stu-id="f606b-125">All cmdlets have online help.</span></span> <span data-ttu-id="f606b-126">O exemplo a seguir mostra como exibir a ajuda online para o cmdlet `New-PowerPivotServiceApplication`:</span><span class="sxs-lookup"><span data-stu-id="f606b-126">The following example shows how to view the online help for the `New-PowerPivotServiceApplication` cmdlet:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Full  
    ```  
  
     <span data-ttu-id="f606b-127">Como alternativa, para exibir apenas os exemplos, use a sintaxe a seguir:</span><span class="sxs-lookup"><span data-stu-id="f606b-127">Alternatively, to view just the examples, use the following syntax:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Example  
    ```  
  
## <a name="enable-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="f606b-128">Habilitar cmdlets do PowerPivot em um servidor</span><span class="sxs-lookup"><span data-stu-id="f606b-128">Enable PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="f606b-129">Os cmdlets do PowerPivot estão disponíveis depois que você instala o PowerPivot para SharePoint e implanta a solução de farm.</span><span class="sxs-lookup"><span data-stu-id="f606b-129">PowerPivot cmdlets are available after you install PowerPivot for SharePoint and deploy the farm solution.</span></span> <span data-ttu-id="f606b-130">As soluções são implantadas quando você executa a ferramenta de Configuração do PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="f606b-130">The solutions are deployed when you ran the PowerPivot Configuration tool.</span></span> <span data-ttu-id="f606b-131">Siga estas etapas para habilitar o uso de cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f606b-131">Follow these steps to enable the use of cmdlets:</span></span>  
  
1.  <span data-ttu-id="f606b-132">Abra um Shell de Gerenciamento do SharePoint usando a opção **Executar como Administrador** .</span><span class="sxs-lookup"><span data-stu-id="f606b-132">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="f606b-133">Execute o primeiro cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f606b-133">Run the first cmdlet:</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="f606b-134">O cmdlet retorna o nome da solução, sua ID de solução e Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="f606b-134">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="f606b-135">Na próxima etapa, você implantará a solução.</span><span class="sxs-lookup"><span data-stu-id="f606b-135">In the next step, you deploy the solution.</span></span>  
  
3.  <span data-ttu-id="f606b-136">Execute o segundo cmdlet para implantar a solução:</span><span class="sxs-lookup"><span data-stu-id="f606b-136">Run the second cmdlet to deploy the solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
4.  <span data-ttu-id="f606b-137">Feche a janela.</span><span class="sxs-lookup"><span data-stu-id="f606b-137">Close the window.</span></span> <span data-ttu-id="f606b-138">Abra-a novamente usando a opção **Executar como Administrador** .</span><span class="sxs-lookup"><span data-stu-id="f606b-138">Reopen it, again using the **Run as Administrator** option.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="f606b-139">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="f606b-139">Related Content</span></span>  
 [<span data-ttu-id="f606b-140">Administração e configuração de servidor do PowerPivot na Administração Central</span><span class="sxs-lookup"><span data-stu-id="f606b-140">PowerPivot Server Administration and Configuration in Central Administration</span></span>](power-pivot-server-administration-and-configuration-in-central-administration.md)  
  
 [<span data-ttu-id="f606b-141">PowerPivot Configuration Tools</span><span class="sxs-lookup"><span data-stu-id="f606b-141">PowerPivot Configuration Tools</span></span>](power-pivot-configuration-tools.md)  
  
 [<span data-ttu-id="f606b-142">Referência do PowerShell para PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="f606b-142">PowerShell Reference for PowerPivot for SharePoint</span></span>](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint)  
