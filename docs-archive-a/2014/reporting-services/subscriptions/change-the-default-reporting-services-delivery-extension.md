---
title: Alterar a extensão de entrega padrão do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], default delivery extension
ms.assetid: 5f6fee72-01bf-4f6c-85d2-7863c46c136b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cc1b3af2a4fe3038b761d0b48030062da06d354e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682076"
---
# <a name="change-the-default-reporting-services-delivery-extension"></a><span data-ttu-id="c0dbb-102">Alterar a extensão de entrega padrão do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c0dbb-102">Change the Default Reporting Services Delivery Extension</span></span>
  <span data-ttu-id="c0dbb-103">Você pode modificar as definições de configuração do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para alterar a extensão de entrega padrão que aparece na lista **Entregue por** de uma página de definição de assinatura.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-103">You can modify [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration settings to change the default delivery extension that appears in the **Delivered by** list of a subscription definition page.</span></span> <span data-ttu-id="c0dbb-104">Por exemplo, você pode modificar a configuração de modo que quando os usuários criem uma nova assinatura, a entrega de compartilhamento de arquivos seja selecionada por padrão, em vez da entrega de email.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-104">For example you can modify the configuration so that when users create a new subscription, file share delivery is selected by default instead of e-mail delivery.</span></span> <span data-ttu-id="c0dbb-105">Você também pode alterar a ordem em que as extensões de entrega são listadas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-105">You can also change the order the delivery extensions are listed in the user interface.</span></span>

 <span data-ttu-id="c0dbb-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] | Modo do SharePoint para [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0dbb-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="c0dbb-107">inclui as entregas de Email e Compartilhamento de Arquivos do Windows como extensões.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-107">includes E-mail and Windows File Share delivery are extensions.</span></span> <span data-ttu-id="c0dbb-108">O servidor de relatório pode ter extensões de entrega adicionais caso extensões personalizadas ou de terceiros tenham sido implantadas para oferecer suporte à entrega personalizada.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-108">Your report server might have additional delivery extensions if you have deployed custom or third-party extensions to support custom delivery.</span></span> <span data-ttu-id="c0dbb-109">A disponibilidade de uma extensão de entrega depende de sua implantação em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-109">The availability of a delivery extension depends on whether it is deployed on a report server.</span></span>

## <a name="default-native-mode-report-server-configuration"></a><span data-ttu-id="c0dbb-110">Configuração padrão de servidor de relatório em modo nativo</span><span class="sxs-lookup"><span data-stu-id="c0dbb-110">Default Native mode report server configuration</span></span>
 <span data-ttu-id="c0dbb-111">A ordem de uma extensão de entrega que aparece no Report Manager na lista **Entregue por** baseia-se na ordem das entradas de extensão de entrega do arquivo **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="c0dbb-111">The order of a delivery extension appears in Report Manager in the **Delivered by** list is based on the order of the delivery extension entries in the **RSReportServer.config** file.</span></span> <span data-ttu-id="c0dbb-112">Por exemplo, a imagem a seguir mostra email em primeiro lugar na lista e é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-112">For example the following image shows e-mail first in the list and it is selected by default.</span></span>

 <span data-ttu-id="c0dbb-113">![lista padrão de extensões de entrega](../media/ssrs-default-delivery.png "lista padrão de extensões de entrega")</span><span class="sxs-lookup"><span data-stu-id="c0dbb-113">![default list of delivery extensions](../media/ssrs-default-delivery.png "default list of delivery extensions")</span></span>

 <span data-ttu-id="c0dbb-114">A seguir está a seção padrão de **RSReportServer.config** , que controla a extensão de entrega padrão e a ordem em que elas são exibidas no Gerenciador de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-114">The following is the default section of **RSReportServer.config** that controls the default delivery extension and the order they are displayed in Report Manager.</span></span> <span data-ttu-id="c0dbb-115">Observe que o email aparece primeiro no arquivo e é definido como o padrão.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-115">Note that email appears first in the file and it is set as the default.</span></span>

```xml
<DeliveryUI>
     <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
          <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
               <Configuration>
               <RSEmailDPConfiguration>
                    <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
               </RSEmailDPConfiguration>
               </Configuration>
     </Extension>
     <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider"/>
</DeliveryUI>
```

#### <a name="configure-file-share-delivery-as-the-default-delivery-extension-in-report-manager"></a><span data-ttu-id="c0dbb-116">Configure a entrega de compartilhamento de arquivos como a extensão de entrega padrão no Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="c0dbb-116">Configure File Share Delivery as the default delivery extension in Report Manager</span></span>

1.  <span data-ttu-id="c0dbb-117">As etapas neste procedimento modificam a configuração para que a entrega de compartilhamento de arquivos seja listada como a primeira opção na interface do usuário e seja a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-117">The steps in this procedure modify the configuration so that file share delivery is listed as the first option in the UI and it is the default selection.</span></span>

     <span data-ttu-id="c0dbb-118">Abra o arquivo RSReportServer.config em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-118">Open the RSReportServer.config file in a text editor.</span></span> <span data-ttu-id="c0dbb-119">Para obter mais informações sobre o arquivo de configuração, confira [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="c0dbb-119">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span> <span data-ttu-id="c0dbb-120">Após a configuração ter sido alterada, a interface do usuário será semelhante à imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="c0dbb-120">After the configuration changes, the UI will look like the following image:</span></span>

     <span data-ttu-id="c0dbb-121">![lista modificada de extensões de entrega](../media/ssrs-modified-delivery.png "lista modificada de extensões de entrega")</span><span class="sxs-lookup"><span data-stu-id="c0dbb-121">![modified list of delivery extensions](../media/ssrs-modified-delivery.png "modified list of delivery extensions")</span></span>

2.  <span data-ttu-id="c0dbb-122">Modifique a seção DeliveryUI para se parecer com o exemplo a seguir e observe as principais alterações:</span><span class="sxs-lookup"><span data-stu-id="c0dbb-122">Modify the DeliveryUI section to look like the following sample and note the key changes of:</span></span>

    1.  <span data-ttu-id="c0dbb-123">A extensão de compartilhamento de arquivos fica antes da extensão de email.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-123">The FileShare extension is before the email extension.</span></span> <span data-ttu-id="c0dbb-124">Isso vai alterar a ordem em que as extensões são listadas no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-124">This will change the order the extensions are listed in Report Manager.</span></span>

    2.  <span data-ttu-id="c0dbb-125">A extensão de compartilhamento de arquivos contém a marca DefaultExtension `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` e a marca de fim de extensão `</Extension>`foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-125">The File share extension contains DefaultExtension tag `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` and the extension end tag was added `</Extension>`.</span></span>

    3.  <span data-ttu-id="c0dbb-126">A extensão de email não está mais configurada como o padrão.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-126">The email extension is no longer configured as the default.</span></span> `<DefaultDeliveryExtension>False</DefaultDeliveryExtension>`

    ```
    <DeliveryUI>
         <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider">
              <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
         </Extension>
         <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
         <DefaultDeliveryExtension>False</DefaultDeliveryExtension>
         <Configuration>
              <RSEmailDPConfiguration>
                   <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
              </RSEmailDPConfiguration>
         </Configuration>
         </Extension>
    </DeliveryUI>
    ```

3.  <span data-ttu-id="c0dbb-127">Salve o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-127">Save the configuration file.</span></span>

4.  <span data-ttu-id="c0dbb-128">Em alguns minutos, o servidor de relatório recarregará o arquivo de configuração e as novas configurações se efetivarão.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-128">Within a few minutes the report server will reload the configuration file and the new settings will take effect.</span></span> <span data-ttu-id="c0dbb-129">Você pode reiniciar o serviço do servidor de relatório para forçar o carregamento do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-129">You can restart the report server service to force the loading of the configuration file.</span></span>

     <span data-ttu-id="c0dbb-130">O evento a seguir é gravado no log de eventos do Windows quando a configuração é lida.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-130">The following event is written to the windows event log when the configuration is read.</span></span>

     <span data-ttu-id="c0dbb-131">**ID de evento:** 109</span><span class="sxs-lookup"><span data-stu-id="c0dbb-131">**Event ID:** 109</span></span>

     <span data-ttu-id="c0dbb-132">**Fonte:** Serviço Windows do Servidor de Relatórios (nome da instância)</span><span class="sxs-lookup"><span data-stu-id="c0dbb-132">**Source:** Report Server Windows Service (instance name)</span></span>

     <span data-ttu-id="c0dbb-133">O arquivo RSReportServer.config foi modificado</span><span class="sxs-lookup"><span data-stu-id="c0dbb-133">The RSReportServer.config file has been modified</span></span>

## <a name="sharepoint-mode-report-servers"></a><span data-ttu-id="c0dbb-134">Servidores de relatório no modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c0dbb-134">SharePoint mode report servers</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="c0dbb-135">O modo do SharePoint armazena informações de extensões nos bancos de dados de aplicativo do serviço SharePoint e não no arquivo RsrReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-135">SharePoint mode stores extensions information in the SharePoint service application databases and not in the RsrReportServer.config file.</span></span> <span data-ttu-id="c0dbb-136">No modo do SharePoint, a configuração de extensão de entrega é modificada usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-136">In SharePoint mode, delivery extension configuration is modified using PowerShell.</span></span>

#### <a name="configure-the-default-delivery-extension"></a><span data-ttu-id="c0dbb-137">Configurar a extensão de entrega padrão</span><span class="sxs-lookup"><span data-stu-id="c0dbb-137">Configure the default delivery extension</span></span>

1.  <span data-ttu-id="c0dbb-138">Abra o **Shell de Gerenciamento do SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-138">Open the **SharePoint Management Shell**.</span></span>

2.  <span data-ttu-id="c0dbb-139">Você poderá ignorar esta etapa se já souber o nome do seu aplicativo de serviço [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0dbb-139">You can skip this step if you already know the name of your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="c0dbb-140">Use o PowerShell a seguir para listar os aplicativos de serviço [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] no seu farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c0dbb-140">Use the following PowerShell to list the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service applications in your SharePoint farm.</span></span>

    ```powershell
    Get-SPRSServiceApplication | Format-List *
    ```

3.  <span data-ttu-id="c0dbb-141">Execute o PowerShell a seguir para verificar a extensão de entrega padrão atual para o aplicativo de serviço "ssrsapp" do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0dbb-141">Run the following PowerShell to verify the current default delivery extension for the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application "ssrsapp".</span></span>

    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -Like "ssrsapp*"};
    Get-SPRSExtension -Identity $app | Where {$_.ServerDirectivesXML -Like "<DefaultDelivery*"} | Format-List *
    ```

## <a name="see-also"></a><span data-ttu-id="c0dbb-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0dbb-142">See Also</span></span>
 <span data-ttu-id="c0dbb-143">[Arquivo](../report-server/rsreportserver-config-configuration-file.md) de configuração RSReportServer envio de arquivo de configuração [RSReportServer](../report-server/rsreportserver-config-configuration-file.md) [compartilhamento de arquivos no Reporting Services](file-share-delivery-in-reporting-services.md) [entrega de email no Reporting Services](e-mail-delivery-in-reporting-services.md) [configurar um servidor de relatório para entrega de email &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)</span><span class="sxs-lookup"><span data-stu-id="c0dbb-143">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [File Share Delivery in Reporting Services](file-share-delivery-in-reporting-services.md) [E-Mail Delivery in Reporting Services](e-mail-delivery-in-reporting-services.md) [Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)</span></span>
