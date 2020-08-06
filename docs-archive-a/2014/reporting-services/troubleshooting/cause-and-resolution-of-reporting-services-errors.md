---
title: Causa e resolução de erros do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- messages [Reporting Services]
- errors [Reporting Services]
- troubleshooting [Reporting Services], errors
ms.assetid: 3db0fef3-37f8-40d0-acc7-1928760dc0e9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa98b9f760485b80f4fa4ac74f3b8008dc3bbec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680770"
---
# <a name="cause-and-resolution-of-reporting-services-errors"></a><span data-ttu-id="7aa1a-102">Causa e resolução de erros do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7aa1a-102">Cause and Resolution of Reporting Services Errors</span></span>
  <span data-ttu-id="7aa1a-103">Este tópico contém informações sobre causas e resoluções para diversos erros relacionados ao [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aa1a-103">This topic contains cause and resolution information for a number of errors related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="7aa1a-104">Os tópicos de mensagem de erro nesta seção fornecem uma explicação da mensagem de erro, possíveis causas e ações para a correção do problema.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-104">The error message topics in this section provide an explanation of the error message, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7aa1a-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7aa1a-105">In This Section</span></span>  
  
|<span data-ttu-id="7aa1a-106">Erro</span><span class="sxs-lookup"><span data-stu-id="7aa1a-106">Error</span></span>|<span data-ttu-id="7aa1a-107">Mensagem</span><span class="sxs-lookup"><span data-stu-id="7aa1a-107">Message</span></span>|  
|-----------|-------------|  
|[<span data-ttu-id="7aa1a-108">rsAccessedDenied – Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7aa1a-108">rsAccessedDenied - Reporting Services Error</span></span>](rsaccesseddenied-reporting-services-error.md)|<span data-ttu-id="7aa1a-109">As permissões concedidas ao usuário 'meudomínio\minhaConta' são insuficientes para a execução dessa operação.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-109">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="7aa1a-110">(rsAccessDenied) (ReportingServicesLibrary).</span><span class="sxs-lookup"><span data-stu-id="7aa1a-110">(rsAccessDenied) (ReportingServicesLibrary).</span></span>|  
|[<span data-ttu-id="7aa1a-111">rsInternalError – Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7aa1a-111">rsInternalError - Reporting Services Error</span></span>](rsinternalerror-reporting-services-error.md)|<span data-ttu-id="7aa1a-112">Um erro interno ocorreu no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-112">An internal error occurred on the report server.</span></span> <span data-ttu-id="7aa1a-113">Consulte o log de erros para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-113">See the error log for more details.</span></span>|  
|[<span data-ttu-id="7aa1a-114">rsModelGenerationError – Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7aa1a-114">rsModelGenerationError - Reporting Services Error</span></span>](rsmodelgenerationerror-reporting-services-error.md)|<span data-ttu-id="7aa1a-115">Erro ao gerar modelo.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-115">An error occurred while generating model.</span></span> <span data-ttu-id="7aa1a-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span></span>|  
|[<span data-ttu-id="7aa1a-117">rsProcessingError – Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7aa1a-117">rsProcessingError - Reporting Services Error</span></span>](rsprocessingerror-reporting-services-error.md)|<span data-ttu-id="7aa1a-118">Ocorreram erros em processamento de relatório.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-118">Errors have occurred in report processing.</span></span>|  
|[<span data-ttu-id="7aa1a-119">rsServerConfigurationError – Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7aa1a-119">rsServerConfigurationError - Reporting Services Error</span></span>](rsserverconfigurationerror-reporting-services-error.md)|<span data-ttu-id="7aa1a-120">O servidor de relatório encontrou um erro de configuração.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-120">The report server has encountered a configuration error.</span></span>|  
|[<span data-ttu-id="7aa1a-121">rrRenderingError – Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7aa1a-121">rrRenderingError - Reporting Services Error</span></span>](rrrenderingerror-reporting-services-error.md)|<span data-ttu-id="7aa1a-122">Ocorreu um erro na renderização do relatório.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-122">An error occurred during rendering of the report.</span></span> <span data-ttu-id="7aa1a-123">(rrRenderingError) %1.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-123">(rrRenderingError) %1.</span></span>|  
|[<span data-ttu-id="7aa1a-124">Serviço Windows Servidor de Relatório &#40;MSSQLServer&#41; 107</span><span class="sxs-lookup"><span data-stu-id="7aa1a-124">Report Server Windows Service &#40;MSSQLServer&#41; 107</span></span>](../../relational-databases/errors-events/mssqlserver-107-database-engine-error.md)|<span data-ttu-id="7aa1a-125">O serviço Servidor de Relatórios do Windows (MSSQLSERVER) não pode estabelecer conexão com o banco de dados do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="7aa1a-125">Report Server Windows service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7aa1a-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7aa1a-126">See Also</span></span>  
 <span data-ttu-id="7aa1a-127">[Fontes e arquivos de log do Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="7aa1a-127">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="7aa1a-128">Referência de erros e eventos &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7aa1a-128">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](errors-and-events-reference-reporting-services.md)  
  
  
