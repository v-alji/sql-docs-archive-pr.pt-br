---
title: MSSQLSERVER_33028 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33028 (Database Engine error)
ms.assetid: c5cec0e4-0bcd-4907-826f-e7d835cfcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 555dcf0220793abc0e8af81b3f56867f9960c5f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573064"
---
# <a name="mssqlserver_33028"></a><span data-ttu-id="b85af-102">MSSQLSERVER_33028</span><span class="sxs-lookup"><span data-stu-id="b85af-102">MSSQLSERVER_33028</span></span>
    
## <a name="details"></a><span data-ttu-id="b85af-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b85af-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b85af-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="b85af-104">Product Name</span></span>|<span data-ttu-id="b85af-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b85af-105">SQL Server</span></span>|  
|<span data-ttu-id="b85af-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="b85af-106">Event ID</span></span>|<span data-ttu-id="b85af-107">33028</span><span class="sxs-lookup"><span data-stu-id="b85af-107">33028</span></span>|  
|<span data-ttu-id="b85af-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="b85af-108">Event Source</span></span>|<span data-ttu-id="b85af-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b85af-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b85af-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b85af-110">Component</span></span>|<span data-ttu-id="b85af-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b85af-111">SQLEngine</span></span>|  
|<span data-ttu-id="b85af-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="b85af-112">Symbolic Name</span></span>|<span data-ttu-id="b85af-113">SEC_CRYPTOPROV_CANTOPENSESSION</span><span class="sxs-lookup"><span data-stu-id="b85af-113">SEC_CRYPTOPROV_CANTOPENSESSION</span></span>|  
|<span data-ttu-id="b85af-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="b85af-114">Message Text</span></span>|<span data-ttu-id="b85af-115">Não é possível abrir a sessão para %S_MSG '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="b85af-115">Cannot open session for %S_MSG '%.\*ls'.</span></span> <span data-ttu-id="b85af-116">Código de erro do provedor: %d.</span><span class="sxs-lookup"><span data-stu-id="b85af-116">Provider error code: %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b85af-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="b85af-117">Explanation</span></span>  
 <span data-ttu-id="b85af-118">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde abrir o provedor criptográfico listado na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b85af-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to open the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="b85af-119">O provedor criptográfico forneceu o código de erro listado.</span><span class="sxs-lookup"><span data-stu-id="b85af-119">The cryptographic provider supplied the error code listed.</span></span> <span data-ttu-id="b85af-120">Você talvez precise contatar seu provedor criptográfico para obter mais informações sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="b85af-120">You may need to contact your cryptographic provider for more information about the error.</span></span>  
  
|<span data-ttu-id="b85af-121">Código do erro</span><span class="sxs-lookup"><span data-stu-id="b85af-121">Error code</span></span>|<span data-ttu-id="b85af-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="b85af-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="b85af-123">0</span><span class="sxs-lookup"><span data-stu-id="b85af-123">0</span></span>|<span data-ttu-id="b85af-124">Sucesso.</span><span class="sxs-lookup"><span data-stu-id="b85af-124">Success.</span></span> <span data-ttu-id="b85af-125">Nenhum erro.</span><span class="sxs-lookup"><span data-stu-id="b85af-125">No error.</span></span>|  
|<span data-ttu-id="b85af-126">1</span><span class="sxs-lookup"><span data-stu-id="b85af-126">1</span></span>|<span data-ttu-id="b85af-127">Falha.</span><span class="sxs-lookup"><span data-stu-id="b85af-127">Failure.</span></span> <span data-ttu-id="b85af-128">Ocorreu um erro não especificado ou inesperado.</span><span class="sxs-lookup"><span data-stu-id="b85af-128">An unspecified or unexpected error occurred.</span></span> <span data-ttu-id="b85af-129">Não há informações adicionais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b85af-129">Additional information is not available.</span></span>|  
|<span data-ttu-id="b85af-130">2</span><span class="sxs-lookup"><span data-stu-id="b85af-130">2</span></span>|<span data-ttu-id="b85af-131">Buffer insuficiente.</span><span class="sxs-lookup"><span data-stu-id="b85af-131">Insufficient Buffer.</span></span> <span data-ttu-id="b85af-132">Não foi possível alocar espaço para o provedor criptográfico.</span><span class="sxs-lookup"><span data-stu-id="b85af-132">Space could not be allocated for the cryptographic provider.</span></span>|  
|<span data-ttu-id="b85af-133">3</span><span class="sxs-lookup"><span data-stu-id="b85af-133">3</span></span>|<span data-ttu-id="b85af-134">Sem suporte.</span><span class="sxs-lookup"><span data-stu-id="b85af-134">Not Supported.</span></span> <span data-ttu-id="b85af-135">Não há suporte para o provedor criptográfico nesta versão.</span><span class="sxs-lookup"><span data-stu-id="b85af-135">The cryptographic provider is not supported by this release.</span></span> <span data-ttu-id="b85af-136">Selecione outro provedor criptográfico.</span><span class="sxs-lookup"><span data-stu-id="b85af-136">Select another cryptographic provider.</span></span>|  
|<span data-ttu-id="b85af-137">4</span><span class="sxs-lookup"><span data-stu-id="b85af-137">4</span></span>|<span data-ttu-id="b85af-138">Não encontrado.</span><span class="sxs-lookup"><span data-stu-id="b85af-138">Not Found.</span></span> <span data-ttu-id="b85af-139">O provedor criptográfico especificado não está presente ou você não tem autorização para acessar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="b85af-139">The specified cryptographic provider is not present or you do not have authorization to access the files.</span></span>|  
|<span data-ttu-id="b85af-140">5</span><span class="sxs-lookup"><span data-stu-id="b85af-140">5</span></span>|<span data-ttu-id="b85af-141">Falha de autorização.</span><span class="sxs-lookup"><span data-stu-id="b85af-141">Authorization Failure.</span></span> <span data-ttu-id="b85af-142">Talvez uma senha ou um nome de usuário incorreto tenha sido fornecido durante a criação da credencial.</span><span class="sxs-lookup"><span data-stu-id="b85af-142">Can result from providing an incorrect password or username when creating the credential.</span></span> <span data-ttu-id="b85af-143">Pode ocorrer quando a credencial não existe.</span><span class="sxs-lookup"><span data-stu-id="b85af-143">Can result if the credential does not exist.</span></span>|  
|<span data-ttu-id="b85af-144">6</span><span class="sxs-lookup"><span data-stu-id="b85af-144">6</span></span>|<span data-ttu-id="b85af-145">Argumento inválido.</span><span class="sxs-lookup"><span data-stu-id="b85af-145">Invalid Argument.</span></span> <span data-ttu-id="b85af-146">Um argumento inválido foi passado ao provedor criptográfico.</span><span class="sxs-lookup"><span data-stu-id="b85af-146">An invalid argument was passed to the cryptographic provider.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="b85af-147">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="b85af-147">User Action</span></span>  
 <span data-ttu-id="b85af-148">Resolva o erro ou contate o provedor criptográfico para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b85af-148">Resolve the error, or contact the cryptographic provider for more information.</span></span>  
  
  
