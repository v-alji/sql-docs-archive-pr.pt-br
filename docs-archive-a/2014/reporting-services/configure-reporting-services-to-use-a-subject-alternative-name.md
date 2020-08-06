---
title: Configurar Reporting Services para usar um nome alternativo da entidade | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ce458f9f-4b4f-4a58-aa75-9a90dda1e622
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0312d2d1fff8f854eb2ffb8d0dad2563212ee23b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684600"
---
# <a name="configure-reporting-services-to-use-a-subject-alternative-name"></a><span data-ttu-id="ce712-102">Configurar o Reporting Services para usar um nome alternativo da entidade</span><span class="sxs-lookup"><span data-stu-id="ce712-102">Configure Reporting Services to Use a Subject Alternative Name</span></span>
  <span data-ttu-id="ce712-103">Este tópico explica como configurar o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) para usar um SAN (Nome alternativo da entidade) modificando o arquivo rsreportserver.config e usando a ferramenta Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="ce712-103">This topic explains how to configure [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) to use a subject alternative name (SAN) by modifying the rsreportserver.config file and using the Netsh.exe tool.</span></span>

||
|-|
|<span data-ttu-id="ce712-104">**[!INCLUDE[applies](../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Modo nativo</span><span class="sxs-lookup"><span data-stu-id="ce712-104">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Native mode</span></span>|

 <span data-ttu-id="ce712-105">As instruções aplicam-se à URL do Reporting Service e à URL do Serviço Web.</span><span class="sxs-lookup"><span data-stu-id="ce712-105">The instructions apply to the Reporting Service URL as well as a Web Service URL.</span></span>

 <span data-ttu-id="ce712-106">Para usar um SAN, o certificado SSL deve estar registrado no servidor, assinado e ter a chave privada.</span><span class="sxs-lookup"><span data-stu-id="ce712-106">To use a SAN, the SSL certificate must be registered on the server, signed, and have the private key.</span></span> <span data-ttu-id="ce712-107">Você não pode usar um certificado autoassinado</span><span class="sxs-lookup"><span data-stu-id="ce712-107">You cannot use a self-signed certificate</span></span>

 <span data-ttu-id="ce712-108">Você pode configurar as URLs do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para usarem um certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="ce712-108">URLs in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] can be configured to use an SSL certificate.</span></span> <span data-ttu-id="ce712-109">Um certificado normalmente tem apenas um nome de entidade, o que permite apenas uma URL por sessão SSL (protocolo SSL).</span><span class="sxs-lookup"><span data-stu-id="ce712-109">A certificate normally has just a subject name, which allows only one URL for an SSL (Secure Sockets Layer) session.</span></span> <span data-ttu-id="ce712-110">O SAN é um campo adicional no certificado que permite que um serviço SSL ouça e seja válido para muitas URLs e compartilhe a porta SSL com outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ce712-110">The SAN is an additional field in the certificate that allows an SSL service to listen and be valid for many URLs, and to share the SSL port with other applications.</span></span> <span data-ttu-id="ce712-111">O SAN é semelhante ao seguinte: www.s2.com.</span><span class="sxs-lookup"><span data-stu-id="ce712-111">The SAN looks something like the following: www.s2.com.</span></span>

 <span data-ttu-id="ce712-112">Para obter mais informações sobre configurações SSL para [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], consulte [Configurar conexões SSL em um servidor de relatório do modo nativo](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="ce712-112">For more information about SSL settings for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Configure SSL Connections on a Native Mode Report Server](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span></span>

### <a name="configure-ssrs-to-use-a-subject-alternative-name-for-web-service-url"></a><span data-ttu-id="ce712-113">Configurar o SSRS para usar um nome alternativo da entidade para a URL do Web Service</span><span class="sxs-lookup"><span data-stu-id="ce712-113">Configure SSRS to use a subject alternative name for Web Service URL</span></span>

1.  <span data-ttu-id="ce712-114">Iniciar o Gerenciador de Configuração do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ce712-114">Start Reporting Services Configuration Manager.</span></span>

     <span data-ttu-id="ce712-115">Para obter mais informações, consulte [Reporting Services Configuration Manager &#40;Modo Nativo&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="ce712-115">For more information, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>

2.  <span data-ttu-id="ce712-116">Na página **URL do Serviço Web** , escolha uma porta SSL e o certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="ce712-116">On the **Web Service URL** page, select an SSL port and SSL Certificate.</span></span>

     <span data-ttu-id="ce712-117">![Gerenciador de Configurações do Reporting Services](media/reportingservices-configurationmanager.png "Gerenciador de Configurações do Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="ce712-117">![Reporting Services Configuration Manager](media/reportingservices-configurationmanager.png "Reporting Services Configuration Manager")</span></span>

     <span data-ttu-id="ce712-118">O gerente de configuração registra o certificado SSL para a porta.</span><span class="sxs-lookup"><span data-stu-id="ce712-118">The configuration manager registers the SSL certificate for the port.</span></span>

3.  <span data-ttu-id="ce712-119">Abra o arquivo rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="ce712-119">Open the rsreportserver.config file.</span></span>

     <span data-ttu-id="ce712-120">Para o SSRS no modo Nativo, o arquivo RSReportServer.config está localizado por padrão na pasta abaixo.</span><span class="sxs-lookup"><span data-stu-id="ce712-120">For SSRS Native mode, the file is located by default in the following folder.</span></span>

    ```
    \Program Files\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer
    ```

4.  <span data-ttu-id="ce712-121">Copie a seção da URL para o aplicativo Report Server Web Service.</span><span class="sxs-lookup"><span data-stu-id="ce712-121">Copy the URL section for the Report Server Web Service application.</span></span>

     <span data-ttu-id="ce712-122">Por exemplo, esta é a seção de URL original.</span><span class="sxs-lookup"><span data-stu-id="ce712-122">For example, the following is the original URL section.</span></span>

    ```
        <URL>
         <UrlString>https://localhost:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

     <span data-ttu-id="ce712-123">Esta é a seção de URL modificada.</span><span class="sxs-lookup"><span data-stu-id="ce712-123">The following is the modified URL section.</span></span>

    ```
    <URL>
         <UrlString>https://www.s1.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>
        <URL>
         <UrlString>https://www.s2.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

5.  <span data-ttu-id="ce712-124">Salve o arquivo rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="ce712-124">Save the rsreportserver.config file.</span></span>

6.  <span data-ttu-id="ce712-125">Inicie um prompt de comando como administrador e execute a ferramenta Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="ce712-125">Start a command prompt as an administrator, and run the Netsh.exe tool.</span></span>

    ```
    C:\windows\system32\netsh
    ```

7.  <span data-ttu-id="ce712-126">Mude para o contexto http, digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ce712-126">Switch to the http context by typing the following.</span></span>

    ```
    Netsh>http
    ```

8.  <span data-ttu-id="ce712-127">Mostre as urlacls existentes digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ce712-127">Show the existing urlacls by typing the following.</span></span>

    ```
    Netsh http>show urlacl
    ```

     <span data-ttu-id="ce712-128">Uma entrada como a seguinte é exibida:</span><span class="sxs-lookup"><span data-stu-id="ce712-128">An entry such as the following appears.</span></span>

    ```
    Reserved URL            : https:// www.s1.com:443/ReportServer/
        User: NT SERVICE\ReportServer
            Listen: Yes
            Delegate: No
            SDDL: D:(A;;GX;;;S-1-5-80-1234567890-123456789-123456789-123456789-1234567890)
    ```

     <span data-ttu-id="ce712-129">Uma urlacl é uma DACL (lista de controle de acesso discricionário) para uma URL reservada.</span><span class="sxs-lookup"><span data-stu-id="ce712-129">An urlacl is a DACL (Discretionary Access Control List) for a reserved URL.</span></span>

9. <span data-ttu-id="ce712-130">Crie uma nova entrada para o nome alternativo da entidade, com o mesmo usuário e SDDL que a entrada existente, digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ce712-130">Create a new entry for the subject alternative name, with the same user and SDDL as the existing entry, by typing the following.</span></span>

    ```
    netsh http>add urlacl  url=https://www.s2.com:443/ReportServer  
    user="NT Service\ReportServer" sddl=D:(A;;GX;;;S-1-5-80-1234567980-12346579-123456789-123456789-1234567890)

    ```

10. <span data-ttu-id="ce712-131">Na página **Status do Servidor de Relatório** do Gerenciador de Configuração do Reporting Services, clique em **Parar** e clique em **Iniciar** para reiniciar o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ce712-131">On the **Report Server Status** page of the Reporting Services Configuration Manager, Click **Stop** and then click **Start** to restart the report server.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce712-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ce712-132">See Also</span></span>
 <span data-ttu-id="ce712-133">O [arquivo de configuração RSReportServer](report-server/rsreportserver-config-configuration-file.md) [Gerenciador de configurações do Reporting Services &#40;modo nativo&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [modificar um arquivo de configuração de Reporting Services &#40;RSreportserver.config](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md)&#41;[configurar as URLs do servidor de relatório &#40;SSRS Configuration Manager](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="ce712-133">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)</span></span>


