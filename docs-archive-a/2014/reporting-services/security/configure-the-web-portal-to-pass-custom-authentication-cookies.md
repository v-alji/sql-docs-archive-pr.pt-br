---
title: Configurar Report Manager para passar cookies de autenticação personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: 91aeb053-149e-4562-ae4c-a688d0e1b2ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 90e8798fb91152ec64e7f290dc1522fc8eaa451c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571266"
---
# <a name="configure-report-manager-to-pass-custom-authentication-cookies"></a><span data-ttu-id="0f126-102">Configurar o Gerenciador de Relatórios para transmitir cookies de autenticação personalizados</span><span class="sxs-lookup"><span data-stu-id="0f126-102">Configure Report Manager to Pass Custom Authentication Cookies</span></span>
  <span data-ttu-id="0f126-103">Se você estiver usando uma extensão de autenticação personalizada, configure o Gerenciador de Relatórios para transmitir cookies de autenticação personalizados.</span><span class="sxs-lookup"><span data-stu-id="0f126-103">If you are using a custom authentication extension, you should configure Report Manager to transmit custom authentication cookies.</span></span> <span data-ttu-id="0f126-104">Caso contrário, o Gerenciador de Relatórios transmitirá cookies somente por solicitações HTTP específicas do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0f126-104">Otherwise, Report Manager will only transmit cookies through HTTP requests specific to the report server.</span></span> <span data-ttu-id="0f126-105">Se desejar transmitir cookies adicionais, modifique o arquivo RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="0f126-105">If you want to transmit additional cookies, you must modify the RSReportServer.Config file.</span></span>  
  
## <a name="modifying-the-rsreportserverconfig-file"></a><span data-ttu-id="0f126-106">Modificando o arquivo RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="0f126-106">Modifying the RSReportServer.Config File</span></span>  
 <span data-ttu-id="0f126-107">Você pode habilitar a Report Manager para transmitir cookies adicionais por meio do servidor de relatório adicionando um `PassThroughCookies` elemento de> de <para as definições de configuração de Report Manager no arquivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="0f126-107">You can enable Report Manager to transmit additional cookies through to the report server by adding a <`PassThroughCookies`> element to the Report Manager configuration settings in the RSReportServer.config file.</span></span> <span data-ttu-id="0f126-108">A transmissão de cookies adicionais é útil em uma solução de autenticação de logon único que requer não só cookies de autenticação do servidor de relatório, mas também cookies de um sistema de autenticação de terceiros.</span><span class="sxs-lookup"><span data-stu-id="0f126-108">Transmitting additional cookies is helpful in a single sign-on authentication solution that requires not only the report server authentication cookies, but also cookies from a third-party authentication system.</span></span>  
  
 <span data-ttu-id="0f126-109">Para permitir que cookies adicionais sejam transmitidos através de solicitações HTTP ao usar o Gerenciador de Relatórios, defina os seguintes elementos no arquivo RSReportServer.config:</span><span class="sxs-lookup"><span data-stu-id="0f126-109">To enable additional cookies to be transmitted through HTTP requests when using Report Manager, set the following elements in the RSReportServer.config file:</span></span>  
  
```  
<UI>  
   <CustomAuthenticationUI>  
      ...  
      <PassThroughCookies>  
         <PassThroughCookie>cookiename1</PassThroughCookie>  
         <PassThroughCookie>cookiename2</PassThroughCookie>  
      </PassThroughCookies>  
   </CustomAuthenticationUI>  
      ...  
</UI>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f126-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0f126-110">See Also</span></span>  
 <span data-ttu-id="0f126-111">[Autenticação com o servidor de relatório](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="0f126-111">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="0f126-112">[Arquivo de configuração RSReportServer](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="0f126-112">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="0f126-113">[Visão geral de extensões de segurança](../extensions/security-extension/security-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="0f126-113">[Security Extensions Overview](../extensions/security-extension/security-extensions-overview.md) </span></span>  
 [<span data-ttu-id="0f126-114">Configurar e administrar um servidor de relatório &#40;modo nativo do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0f126-114">Configure and Administer a Report Server &#40;SSRS Native Mode&#41;</span></span>](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md)  
  
  
