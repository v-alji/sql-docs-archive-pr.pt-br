---
title: rsModelGenerationError – Erro do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsModelGenerationError
ms.assetid: 3a0ad63f-87f9-4ca1-b0c2-c85fa991634a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 713de57f0f2957983966f8ef0345bb374c311781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574461"
---
# <a name="rsmodelgenerationerror---reporting-services-error"></a><span data-ttu-id="d11fc-102">rsModelGenerationError - Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d11fc-102">rsModelGenerationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="d11fc-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d11fc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d11fc-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d11fc-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="d11fc-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d11fc-105">Event ID</span></span>|<span data-ttu-id="d11fc-106">rsRenderingError</span><span class="sxs-lookup"><span data-stu-id="d11fc-106">rsRenderingError</span></span>|  
|<span data-ttu-id="d11fc-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d11fc-107">Event Source</span></span>|<span data-ttu-id="d11fc-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="d11fc-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="d11fc-109">Componente</span><span class="sxs-lookup"><span data-stu-id="d11fc-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="d11fc-110">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d11fc-110">Message Text</span></span>|<span data-ttu-id="d11fc-111">Erro ao gerar modelo.</span><span class="sxs-lookup"><span data-stu-id="d11fc-111">An error occurred while generating model.</span></span> <span data-ttu-id="d11fc-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span><span class="sxs-lookup"><span data-stu-id="d11fc-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d11fc-113">Explicação</span><span class="sxs-lookup"><span data-stu-id="d11fc-113">Explanation</span></span>  
 <span data-ttu-id="d11fc-114">O modelo de relatório não pôde ser gerado.</span><span class="sxs-lookup"><span data-stu-id="d11fc-114">The report model could not be generated.</span></span> <span data-ttu-id="d11fc-115">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 e versões anteriores, esse erro terá mais probabilidade de acontecer quando o objeto System.Data.DataSet não for capaz de controlar uma tabela ou relação dentro do esquema de banco de dados, como quando, por exemplo, duas chaves estrangeiras são definidas na mesma coluna em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="d11fc-115">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 and earlier versions, this error is most likely displayed when the System.Data.DataSet object cannot handle a table or relationship within the database schema, such as when, for example, two foreign keys are defined on the same column within a table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d11fc-116">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d11fc-116">User Action</span></span>  
 <span data-ttu-id="d11fc-117">Para determinar o motivo específico que causou essa mensagem de erro, examine os arquivos de log do servidor de relatório, localizados em \Microsoft SQL Server\\<SQL Server Instance\>\Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="d11fc-117">To determine the specific reason that caused this message to appear, review the report server log files, which are located at \Microsoft SQL Server\\<SQL Server Instance\>\Reporting Services\LogFiles.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="d11fc-118">Somente interno</span><span class="sxs-lookup"><span data-stu-id="d11fc-118">Internal-Only</span></span>  
  
