---
title: rsInternalError – erro do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsInternalError
ms.assetid: 52613d52-fc78-4870-93f0-7d393ab9c335
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 85b88519df810f60c580ad2d6eb355dde236d081
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574463"
---
# <a name="rsinternalerror---reporting-services-error"></a><span data-ttu-id="b90e8-102">rsInternalError - Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b90e8-102">rsInternalError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="b90e8-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b90e8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b90e8-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="b90e8-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="b90e8-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="b90e8-105">Event ID</span></span>|<span data-ttu-id="b90e8-106">rsInternalError</span><span class="sxs-lookup"><span data-stu-id="b90e8-106">rsInternalError</span></span>|  
|<span data-ttu-id="b90e8-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="b90e8-107">Event Source</span></span>|<span data-ttu-id="b90e8-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="b90e8-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="b90e8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="b90e8-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="b90e8-110">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="b90e8-110">Message Text</span></span>|<span data-ttu-id="b90e8-111">Um erro interno ocorreu no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="b90e8-111">An internal error occurred on the report server.</span></span> <span data-ttu-id="b90e8-112">Consulte o log de erros para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b90e8-112">See the error log for more details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b90e8-113">Explicação</span><span class="sxs-lookup"><span data-stu-id="b90e8-113">Explanation</span></span>  
 <span data-ttu-id="b90e8-114">Essa é uma mensagem de erro genérica seguida frequentemente por um erro mais descritivo que fornece mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b90e8-114">This is a generic error message that is often followed by a more descriptive error that provides more detail.</span></span>  
  
 <span data-ttu-id="b90e8-115">Erros internos são incomuns.</span><span class="sxs-lookup"><span data-stu-id="b90e8-115">Internal errors are uncommon.</span></span> <span data-ttu-id="b90e8-116">Se esse erro for exibido, mais informações estarão disponíveis nos logs de rastreamento de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="b90e8-116">If you get this error, more information is available in report server trace logs.</span></span> <span data-ttu-id="b90e8-117">Além disso, se estiver executando como administrador local no mesmo computador em que ocorreu o erro, será possível exibir a pilha de chamadas para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b90e8-117">In addition, if you are running as local administrator on the same computer on which the error occurs, you can view the call stack for more information.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b90e8-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="b90e8-118">User Action</span></span>  
 <span data-ttu-id="b90e8-119">Para determinar a causa específica dessa mensagem, examine os arquivos de log do servidor de relatório, que estão localizados em \Microsoft SQL Server\MSRS12. \<instancename > \Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="b90e8-119">To determine the specific cause for this message, review the report server log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="b90e8-120">Para obter mais informações, consulte [Fontes e arquivos de log do Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="b90e8-120">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
 <span data-ttu-id="b90e8-121">Para exibir a pilha de chamadas, clique com o botão direito do mouse na página em que ocorreu o erro e aponte para **Exibir Código-Fonte**.</span><span class="sxs-lookup"><span data-stu-id="b90e8-121">To view the call stack, right-click the page on which the error occurs and point to **View Source**.</span></span> <span data-ttu-id="b90e8-122">A exibição da pilha de chamadas exige permissões de administrador no mesmo computador em que o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="b90e8-122">Viewing the call stack requires administrator permissions on the same computer on which the error occurs.</span></span>  
  
 <span data-ttu-id="b90e8-123">Se não houver nenhuma informação adicional disponível, será possível tentar a solicitação novamente.</span><span class="sxs-lookup"><span data-stu-id="b90e8-123">If there is no additional information available, you can try your request again.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="b90e8-124">Somente interno</span><span class="sxs-lookup"><span data-stu-id="b90e8-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b90e8-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b90e8-125">See Also</span></span>  
 [<span data-ttu-id="b90e8-126">Iniciar e parar o serviço Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="b90e8-126">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
