---
title: Habilitar e desabilitar a impressão do lado do cliente no Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0e709c96-7517-4547-8ef6-5632f8118524
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 031a7cd9b5da07b03b76b6bf49db63572a8fe546
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575582"
---
# <a name="enable-and-disable-client-side-printing-for-reporting-services"></a><span data-ttu-id="7c27c-102">Habilitar e desabilitar a impressão do lado do cliente para Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7c27c-102">Enable and Disable Client-Side Printing for Reporting Services</span></span>
  <span data-ttu-id="7c27c-103">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] controle ActiveX, **RSClientPrint**, fornece impressão do lado do cliente para relatórios exibidos em um navegador.</span><span class="sxs-lookup"><span data-stu-id="7c27c-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX control, **RSClientPrint**, provides client-side printing for reports viewed in a browser.</span></span> <span data-ttu-id="7c27c-104">O controle exibe uma caixa de diálogo de impressão personalizada que oferece suporte aos recursos comuns com outras caixas de diálogo de impressão.</span><span class="sxs-lookup"><span data-stu-id="7c27c-104">The control displays a custom print dialog box that supports features common to other print dialog boxes.</span></span> <span data-ttu-id="7c27c-105">Os recursos incluem a visualização de impressão, as seleções de página para determinar páginas e intervalos específicos, as margens da página e a orientação.</span><span class="sxs-lookup"><span data-stu-id="7c27c-105">The features include print preview, page selections for specifying specific pages and ranges, page margins, and orientation.</span></span> <span data-ttu-id="7c27c-106">Embora a impressão do lado do cliente esteja habilitada por padrão, você pode desabilitar o recurso para impedi-lo de ser usado.</span><span class="sxs-lookup"><span data-stu-id="7c27c-106">Although client-side printing is enabled by default, you can disable the feature to prevent it from being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c27c-107">Baixar controles ActiveX requer permissões de administrador.</span><span class="sxs-lookup"><span data-stu-id="7c27c-107">Downloading ActiveX controls requires administrator permissions.</span></span>  
  
## <a name="downloading-the-activex-control"></a><span data-ttu-id="7c27c-108">Baixando o controle ActiveX</span><span class="sxs-lookup"><span data-stu-id="7c27c-108">Downloading the ActiveX Control</span></span>  
 <span data-ttu-id="7c27c-109">Cada usuário que deseja usar o recurso de impressão deve baixar e instalar o controle ActiveX que oferece a funcionalidade de impressão do cliente.</span><span class="sxs-lookup"><span data-stu-id="7c27c-109">Each user who wants to use the print feature must download and install the ActiveX control that provides client print functionality.</span></span> <span data-ttu-id="7c27c-110">Na primeira vez que um usuário clicar no ícone da **impressora** na barra de ferramentas do relatório, o controle ActiveX da Microsoft será baixado para o computador.</span><span class="sxs-lookup"><span data-stu-id="7c27c-110">The first time a user clicks the **Printer** icon on the report toolbar, the Microsoft ActiveX control is downloaded to the computer.</span></span> <span data-ttu-id="7c27c-111">Depois que o controle for baixado, a caixa de diálogo **Imprimir** será exibida sempre que o usuário clicar no ícone de **impressora** .</span><span class="sxs-lookup"><span data-stu-id="7c27c-111">After the control is downloaded, the **Print** dialog box displays whenever the user clicks the **Printer** icon.</span></span>  
  
 <span data-ttu-id="7c27c-112">Dependendo das configurações do navegador, o usuário pode receber uma solicitação para instalar o controle, ser impedido de instalar o controle ou ter o controle instalado de maneira transparente em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="7c27c-112">Depending on browser settings, the user may be prompted to install the control, be prevented from installing the control, or have the control install transparently in the background.</span></span>  
  
 <span data-ttu-id="7c27c-113">Para [!INCLUDE[msCoName](../../includes/msconame-md.md)] o Internet Explorer, as configurações que afetam o download e a instalação do controle ActiveX são especificadas por meio do nó **controles e plug-ins do ActiveX** na página **configurações de segurança** da zona de conteúdo da Web.</span><span class="sxs-lookup"><span data-stu-id="7c27c-113">For [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, settings that affect ActiveX control download and installation are specified through the **ActiveX controls and plug-ins** node in the **Security Settings** page for the Web content zone.</span></span> <span data-ttu-id="7c27c-114">As seguintes configurações determinam se os usuários podem baixar e executar o controle de impressão, com base nas preferências de segurança da zona da Web:</span><span class="sxs-lookup"><span data-stu-id="7c27c-114">The following settings determine whether users can download and run the print control, based on Web zone security preferences:</span></span>  
  
-   <span data-ttu-id="7c27c-115">Baixe os controles ActiveX assinados.</span><span class="sxs-lookup"><span data-stu-id="7c27c-115">Download signed ActiveX controls.</span></span>  
  
-   <span data-ttu-id="7c27c-116">Controles ActiveX de script marcados para segurança para script.</span><span class="sxs-lookup"><span data-stu-id="7c27c-116">Script ActiveX controls marked safe for scripting.</span></span>  
  
-   <span data-ttu-id="7c27c-117">Execute os controles ActiveX e plug-ins.</span><span class="sxs-lookup"><span data-stu-id="7c27c-117">Run ActiveX controls and plug-ins.</span></span>  
  
 <span data-ttu-id="7c27c-118">Os usuários que desejam usar o **RSClientPrint** para executar a impressão do lado do cliente devem habilitar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7c27c-118">Users who want to use **RSClientPrint** to perform client-side printing must enable the following:</span></span>  
  
-   <span data-ttu-id="7c27c-119">**Baixe controles ActiveX assinados** e o **controle ActiveX de script marcado como seguro para scripts** para fins de instalação.</span><span class="sxs-lookup"><span data-stu-id="7c27c-119">**Download signed ActiveX controls** and **Script ActiveX control marked safe for scripting** for installation purposes.</span></span>  
  
-   <span data-ttu-id="7c27c-120">**Execute controles ActiveX e plug-ins** para operações de impressão em andamento.</span><span class="sxs-lookup"><span data-stu-id="7c27c-120">**Run ActiveX controls and plug-ins** for ongoing print operations.</span></span>  
  
 <span data-ttu-id="7c27c-121">O controle ActiveX **RSClientPrint** é assinado, o que significa que ele contém um certificado digital válido do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c27c-121">The **RSClientPrint** ActiveX control is signed, meaning it contains a valid digital certificate from [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span></span>  
  
## <a name="enabling-and-disabling-client-side-printing"></a><span data-ttu-id="7c27c-122">Habilitando e desabilitando a impressão do lado do cliente</span><span class="sxs-lookup"><span data-stu-id="7c27c-122">Enabling and Disabling Client-Side Printing</span></span>  
 <span data-ttu-id="7c27c-123">Os administradores do servidor de relatório têm a opção de desabilitar o recurso de impressão definindo a propriedade do sistema do servidor de relatório **EnableClientPrinting** como `false` .</span><span class="sxs-lookup"><span data-stu-id="7c27c-123">Report server administrators have the option of disabling the print feature by setting the report server system property **EnableClientPrinting** to `false`.</span></span> <span data-ttu-id="7c27c-124">Isso desabilitará a impressão do lado do cliente para todos os relatórios gerenciados por esse servidor.</span><span class="sxs-lookup"><span data-stu-id="7c27c-124">This will disable client-side printing for all reports managed by that server.</span></span> <span data-ttu-id="7c27c-125">Por padrão, **EnableClientPrinting** é definido como `true` .</span><span class="sxs-lookup"><span data-stu-id="7c27c-125">By default, **EnableClientPrinting** is set to `true`.</span></span> <span data-ttu-id="7c27c-126">Você pode desabilitar a impressão do lado do cliente das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="7c27c-126">You can disable client-side printing in the following ways:</span></span>  
  
-   <span data-ttu-id="7c27c-127">Para um **Servidor de relatório no modo nativo**:</span><span class="sxs-lookup"><span data-stu-id="7c27c-127">For a **Native mode report server**:</span></span>  
  
    1.  <span data-ttu-id="7c27c-128">Inicie o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] com privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="7c27c-128">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    2.  <span data-ttu-id="7c27c-129">Conecte-se a uma instância do servidor de relatório no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c27c-129">Connect to a report server instance in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
    3.  <span data-ttu-id="7c27c-130">Clique com o botão direito do mouse no nó do servidor de relatório e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7c27c-130">Right-click the report server node, and then click **Properties**.</span></span> <span data-ttu-id="7c27c-131">Se a opção **Propriedades** estiver desabilitada, verifique se você iniciou o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] com privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="7c27c-131">If the **Properties** option is disabled, verify you started [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    4.  <span data-ttu-id="7c27c-132">Selecione **habilitar download para o controle de impressão do cliente ActiveX**.</span><span class="sxs-lookup"><span data-stu-id="7c27c-132">Select **Enable download for the ActiveX client print control**.</span></span>  
  
    5.  <span data-ttu-id="7c27c-133">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c27c-133">Click **OK**.</span></span>  
  
-   <span data-ttu-id="7c27c-134">Para um **servidor de relatório no modo do SharePoint**:</span><span class="sxs-lookup"><span data-stu-id="7c27c-134">For a **SharePoint mode report server**:</span></span>  
  
    1.  <span data-ttu-id="7c27c-135">Na Administração Central do SharePoint, clique em **Gerenciamento de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="7c27c-135">In SharePoint Central Administration, click **Application Management**.</span></span>  
  
    2.  <span data-ttu-id="7c27c-136">Clique em **Gerenciar aplicativos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="7c27c-136">Click **Manage service applications**.</span></span>  
  
    3.  <span data-ttu-id="7c27c-137">Clique no nome do aplicativo de serviço do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e clique em **Gerenciar** na faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7c27c-137">Click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application, and then click **Manage** in the SharePoint ribbon.</span></span>  
  
    4.  <span data-ttu-id="7c27c-138">Clique em **Configurações do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="7c27c-138">Click **System Settings**.</span></span>  
  
    5.  <span data-ttu-id="7c27c-139">Selecione **Habilitar Impressão de Cliente**.</span><span class="sxs-lookup"><span data-stu-id="7c27c-139">Select **Enable Client Printing**.</span></span> <span data-ttu-id="7c27c-140">A opção **Habilitar Impressão de Cliente** está próxima à parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="7c27c-140">The **Enable Client Printing** option is near the bottom of the page.</span></span>  
  
    6.  <span data-ttu-id="7c27c-141">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c27c-141">Click **OK**.</span></span>  
  
-   <span data-ttu-id="7c27c-142">Gravar script ou código para definir a propriedade do sistema do servidor de relatório **EnableClientPrinting** como`false.`</span><span class="sxs-lookup"><span data-stu-id="7c27c-142">Write script or code to set the report server system property **EnableClientPrinting** to `false.`</span></span>  
  
 <span data-ttu-id="7c27c-143">O exemplo de script a seguir ilustra uma abordagem para desabilitar a impressão do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="7c27c-143">The following sample script illustrates one approach for disabling client-side printing.</span></span> <span data-ttu-id="7c27c-144">Compile e execute o código a seguir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] para definir a propriedade **EnableClientPrinting** como **False**.</span><span class="sxs-lookup"><span data-stu-id="7c27c-144">Compile and then run the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code to set the **EnableClientPrinting** property to **False**.</span></span> <span data-ttu-id="7c27c-145">Depois de executar o código, reinicialize o IIS.</span><span class="sxs-lookup"><span data-stu-id="7c27c-145">After you run the code, restart IIS.</span></span>  
  
### <a name="sample-script"></a><span data-ttu-id="7c27c-146">Exemplo de Script</span><span class="sxs-lookup"><span data-stu-id="7c27c-146">Sample Script</span></span>  
  
```  
Imports System  
Imports System.Web.Services.Protocols  
Class Sample  
   Public Shared Sub Main()  
Dim rs As New ReportingService()  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
        Dim props(0) As [Property]  
        Dim setProp As New [Property]  
        setProp.Name = "EnableClientPrinting"  
        setProp.Value = "False"   
        props(0) = setProp  
        Try  
            rs.SetSystemProperties(props)  
        Catch ex As System.Web.Services.Protocols.SoapException  
            Console.Write(ex.Detail.InnerXml)  
        Catch e as Exception  
            Console.Write(e.Message)  
        End Try  
    End Sub 'Main  
End Class 'Sample  
```  
  
  
