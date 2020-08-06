---
title: rrRenderingError – erro do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rrRenderingError
ms.assetid: 0751efc3-b81b-44ee-8aac-8560f86ca322
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b44b042c5f3c0cfdb9ffb99d3f45ed073beb972a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680766"
---
# <a name="rrrenderingerror---reporting-services-error"></a><span data-ttu-id="5fef0-102">rrRenderingError - Erro do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5fef0-102">rrRenderingError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="5fef0-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5fef0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fef0-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="5fef0-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="5fef0-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="5fef0-105">Event ID</span></span>|<span data-ttu-id="5fef0-106">rrRenderingError</span><span class="sxs-lookup"><span data-stu-id="5fef0-106">rrRenderingError</span></span>|  
|<span data-ttu-id="5fef0-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="5fef0-107">Event Source</span></span>|<span data-ttu-id="5fef0-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span><span class="sxs-lookup"><span data-stu-id="5fef0-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span></span>|  
|<span data-ttu-id="5fef0-109">Componente</span><span class="sxs-lookup"><span data-stu-id="5fef0-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="5fef0-110">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="5fef0-110">Message Text</span></span>|<span data-ttu-id="5fef0-111">Ocorreu um erro na renderização do relatório.</span><span class="sxs-lookup"><span data-stu-id="5fef0-111">An error occurred during rendering of the report.</span></span> <span data-ttu-id="5fef0-112">(rrRenderingError) %1</span><span class="sxs-lookup"><span data-stu-id="5fef0-112">(rrRenderingError) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5fef0-113">Explicação</span><span class="sxs-lookup"><span data-stu-id="5fef0-113">Explanation</span></span>  
 <span data-ttu-id="5fef0-114">Esta mensagem é retornada quando o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] não puder renderizar ou exportar o relatório.</span><span class="sxs-lookup"><span data-stu-id="5fef0-114">This message is returned when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] cannot render or export the report.</span></span>  
  
 <span data-ttu-id="5fef0-115">Uma mensagem que indica que o tamanho não é suportado, normalmente, é exibida quando o tamanho da página de RDL especificada não é válida.</span><span class="sxs-lookup"><span data-stu-id="5fef0-115">A message that indicates that the size is not supported is typically caused when the specified RDL page size is not valid.</span></span> <span data-ttu-id="5fef0-116">Especifique um tamanho válido de página de RDL e, em seguida, tente novamente.</span><span class="sxs-lookup"><span data-stu-id="5fef0-116">Specify a valid RDL page size and then try again.</span></span>  
  
 <span data-ttu-id="5fef0-117">Uma mensagem que indica que uma medida de tamanho de RDL não é suportada, normalmente, é exibida quando um tipo de unidade sem-suporte é especificado.</span><span class="sxs-lookup"><span data-stu-id="5fef0-117">A message that indicates that an RDL size measurement is not supported is typically caused when an unsupported unit type is specified.</span></span> <span data-ttu-id="5fef0-118">Tipos de unidade válidos são cm, pol, mm, pc e pt.</span><span class="sxs-lookup"><span data-stu-id="5fef0-118">Valid unit types are cm, in, mm, pc, and pt.</span></span> <span data-ttu-id="5fef0-119">Especifique um tipo de unidade válido e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="5fef0-119">Specify a valid unit type and then try again.</span></span>  
  
 <span data-ttu-id="5fef0-120">Uma mensagem que indica que um tamanho negativo não é suportado, normalmente, é exibida quando uma medida negativa para o tamanho da página, por exemplo, -5 cm, é especificada.</span><span class="sxs-lookup"><span data-stu-id="5fef0-120">A message that indicates that a negative size is not supported is typically caused when a negative measurement for the page size, for example -5 cm, is specified.</span></span> <span data-ttu-id="5fef0-121">Especifique um número positivo para o tamanho da página e, em seguida, tente novamente.</span><span class="sxs-lookup"><span data-stu-id="5fef0-121">Specify a positive number for the page size and then try again.</span></span>  
  
 <span data-ttu-id="5fef0-122">Uma mensagem que indica que um tamanho de RDL foi especificado fora de intervalo, normalmente, é exibida quando uma medida para o tamanho da página está fora do tamanho de margem de página válido.</span><span class="sxs-lookup"><span data-stu-id="5fef0-122">A message that indicates that an RDL size is specified out of range is typically caused when a measurement for the page size is outside of the valid page margin size.</span></span> <span data-ttu-id="5fef0-123">Especifique uma medida para o tamanho de página que está dentro dos tamanhos de margem de página válidos.</span><span class="sxs-lookup"><span data-stu-id="5fef0-123">Specify a measurement for the page size that is within the valid page margin sizes.</span></span>  
  
 <span data-ttu-id="5fef0-124">Uma mensagem que indica que uma cor especificada não é suportada, normalmente, é exibida quando uma cor especificada na RDL não é válida.</span><span class="sxs-lookup"><span data-stu-id="5fef0-124">A message that indicates that a color specified is not supported is typically caused when a color specified in the RDL is not valid.</span></span> <span data-ttu-id="5fef0-125">Escolha uma cor suportada pelo RDL e, em seguida, tente novamente.</span><span class="sxs-lookup"><span data-stu-id="5fef0-125">Choose a color supported by RDL and then try again.</span></span>  
  
 <span data-ttu-id="5fef0-126">Uma mensagem que indica que a etiqueta de ação é opcional somente quando estiver usando uma única ação e que a adição de várias ações requer etiquetas para cada ação, normalmente, é exibida quando uma etiqueta de ação é especifica e ela não é válida.</span><span class="sxs-lookup"><span data-stu-id="5fef0-126">A message that indicates that the action label is only optional when using a single action and that adding multiple actions requires labels for each action is typically caused when an action label is specified and it is not valid.</span></span> <span data-ttu-id="5fef0-127">Especifique uma etiqueta de ação válida para cada ação.</span><span class="sxs-lookup"><span data-stu-id="5fef0-127">Specify a valid action label for each action.</span></span>  
  
 <span data-ttu-id="5fef0-128">Uma mensagem que indica que o argumento de estilo tem que ser de um tipo específico, normalmente, é exibida quando um valor de estilo incorreto para o tipo de dados é especificado.</span><span class="sxs-lookup"><span data-stu-id="5fef0-128">A message that indicates the style argument has to be of a specific type is typically caused when an incorrect style value for the data type is specified.</span></span> <span data-ttu-id="5fef0-129">A especificação de RDL identifica os tipos válidos que você pode usar nos valores de estilo de diferentes elementos de RDL.</span><span class="sxs-lookup"><span data-stu-id="5fef0-129">The RDL specification identifies the valid types that you can use in the style values of different RDL elements.</span></span> <span data-ttu-id="5fef0-130">Por exemplo, um valor de estilo incorreto para cor do plano de fundo é "2pt" e o valor incorreto para a altura é "verdade."</span><span class="sxs-lookup"><span data-stu-id="5fef0-130">For example, an incorrect style value for background color is "2pt" and incorrect value for height is "true".</span></span> <span data-ttu-id="5fef0-131">Especifique um valor correto e, em seguida, tente novamente.</span><span class="sxs-lookup"><span data-stu-id="5fef0-131">Specify a correct value and then try again.</span></span>  
  
 <span data-ttu-id="5fef0-132">Uma mensagem que indica que o estilo de borda não é suportado, normalmente, é exibida quando o estilo de borda especificado não é válido.</span><span class="sxs-lookup"><span data-stu-id="5fef0-132">A message that indicates that the border style is not supported is typically caused when the border style specified is not valid.</span></span> <span data-ttu-id="5fef0-133">Especifique um estilo de borda suportado e, em seguida, tente novamente.</span><span class="sxs-lookup"><span data-stu-id="5fef0-133">Specify a supported border style and then try again.</span></span>  
  
 <span data-ttu-id="5fef0-134">Uma mensagem que indica que o mimetype da imagem não é suportado, normalmente, é exibida quando o mimetype especificado para um item de relatório de imagem não é válido.</span><span class="sxs-lookup"><span data-stu-id="5fef0-134">A message that indicates that the image mimetype is not supported is typically caused when the specified mimetype for an image report item is not valid.</span></span> <span data-ttu-id="5fef0-135">Especifique um mimetype com suporte para o item de relatório e, em seguida, tente novamente.</span><span class="sxs-lookup"><span data-stu-id="5fef0-135">Specify a supported mimetype for the report item and then try again.</span></span>  
  
 <span data-ttu-id="5fef0-136">Uma mensagem que indica que o número de linhas excede o máximo de linhas possível por folha, normalmente, é exibida quando o número de linhas em uma planilha do Excel é excedido.</span><span class="sxs-lookup"><span data-stu-id="5fef0-136">A message that indicates that the number of rows exceeds the maximum possible rows per sheet is typically caused when the number of rows in an Excel worksheet is exceeded.</span></span> <span data-ttu-id="5fef0-137">O Excel suporta até 65.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="5fef0-137">Excel supports up to 65,000 rows.</span></span>  
  
 <span data-ttu-id="5fef0-138">Uma mensagem que indica que o número de colunas excede o máximo de colunas possível por folha, normalmente, é exibida quando o número de colunas em uma planilha do Excel é excedido.</span><span class="sxs-lookup"><span data-stu-id="5fef0-138">A message that indicates that the number of columns exceeds the maximum possible columns per sheet is typically caused when the number of columns in an Excel worksheet is exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5fef0-139">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="5fef0-139">User Action</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="5fef0-140">Somente interno</span><span class="sxs-lookup"><span data-stu-id="5fef0-140">Internal-Only</span></span>  
  
