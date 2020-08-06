---
title: rsServerConfigurationError – Erro do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsServerConfigurationError
ms.assetid: 0913afc2-34b4-4713-b570-cfd5718975ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02f8a18c42715d1f118920614eb425820130dacb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684040"
---
# <a name="rsserverconfigurationerror---reporting-services-error"></a><span data-ttu-id="a836c-102">rsServerConfigurationError - Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a836c-102">rsServerConfigurationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="a836c-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a836c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a836c-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a836c-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="a836c-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a836c-105">Event ID</span></span>|<span data-ttu-id="a836c-106">rsServerConfiguration</span><span class="sxs-lookup"><span data-stu-id="a836c-106">rsServerConfiguration</span></span>|  
|<span data-ttu-id="a836c-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a836c-107">Event Source</span></span>|<span data-ttu-id="a836c-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="a836c-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="a836c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a836c-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="a836c-110">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a836c-110">Message Text</span></span>|<span data-ttu-id="a836c-111">O servidor de relatório encontrou um erro de configuração.</span><span class="sxs-lookup"><span data-stu-id="a836c-111">The report server has encountered a configuration error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a836c-112">Explicação</span><span class="sxs-lookup"><span data-stu-id="a836c-112">Explanation</span></span>  
 <span data-ttu-id="a836c-113">Este é um erro geral que ocorre quando o servidor de relatório ou uma ferramenta de criação de relatório tem definições inválidas de configuração.</span><span class="sxs-lookup"><span data-stu-id="a836c-113">This is a general purpose error that occurs when either the report server or a report authoring tool has invalid configuration settings.</span></span> <span data-ttu-id="a836c-114">Normalmente, o erro é acompanhado de uma segunda mensagem que declara a causa real do erro.</span><span class="sxs-lookup"><span data-stu-id="a836c-114">The error is usually accompanied by a second message that states the actual cause of the error.</span></span>  
  
 <span data-ttu-id="a836c-115">A lista a seguir resume as possíveis causas:</span><span class="sxs-lookup"><span data-stu-id="a836c-115">The following list summarizes possible causes:</span></span>  
  
-   <span data-ttu-id="a836c-116">O arquivo RSReportServer.config ou RSReportDesigner.config não pode ser encontrado ou lido.</span><span class="sxs-lookup"><span data-stu-id="a836c-116">The RSReportServer.config or RSReportDesigner.config file cannot be found or read.</span></span>  
  
-   <span data-ttu-id="a836c-117">Os elementos de XML em um desses arquivos de configuração estão ausentes ou são inválidos.</span><span class="sxs-lookup"><span data-stu-id="a836c-117">XML elements in either configuration file are missing or invalid.</span></span>  
  
-   <span data-ttu-id="a836c-118">Os valores para um ou mais elementos de XML estão ausentes ou são inválidos.</span><span class="sxs-lookup"><span data-stu-id="a836c-118">Values for one or more XML elements are missing or invalid.</span></span>  
  
-   <span data-ttu-id="a836c-119">As configurações de registro são inválidas.</span><span class="sxs-lookup"><span data-stu-id="a836c-119">Registry settings are invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a836c-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a836c-120">User Action</span></span>  
 <span data-ttu-id="a836c-121">Se o erro começar a ocorrer após você ter editado manualmente um arquivo de configuração, remova as alterações e insira o valor anterior, ou restaure uma versão anterior se possuir um backup.</span><span class="sxs-lookup"><span data-stu-id="a836c-121">If this error began to occur after you manually edited a configuration file, remove your changes and enter the previous value, or restore a previous version if you have a backup.</span></span>  
  
 <span data-ttu-id="a836c-122">Para examinar as informações adicionais da mensagem de erro que acompanham o `rsServerConfiguration` erro, examine os arquivos de log de rastreamento do servidor de relatório, que estão localizados em \Microsoft SQL Server\MSRS12. \<instancename > \Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="a836c-122">To review additional error message information that accompanies the `rsServerConfiguration` error, review the report server trace log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="a836c-123">Para obter mais informações, consulte [Fontes e arquivos de log do Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="a836c-123">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="a836c-124">Somente interno</span><span class="sxs-lookup"><span data-stu-id="a836c-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a836c-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a836c-125">See Also</span></span>  
 <span data-ttu-id="a836c-126">[Arquivos de configuração do Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="a836c-126">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="a836c-127">Modificar um arquivo de configuração do Reporting Services &#40;RSreportserver.config&#41;</span><span class="sxs-lookup"><span data-stu-id="a836c-127">Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;</span></span>](../report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md)  
  
  
