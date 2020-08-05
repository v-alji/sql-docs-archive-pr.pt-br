---
title: MSSQLSERVER_33027 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33027 (Database Engine error)
ms.assetid: bfdc626e-7958-4511-987d-3b687824e8af
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f6bb461b42b66368224fffd2c14f9b4da61abf5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573065"
---
# <a name="mssqlserver_33027"></a><span data-ttu-id="7ff17-102">MSSQLSERVER_33027</span><span class="sxs-lookup"><span data-stu-id="7ff17-102">MSSQLSERVER_33027</span></span>
    
## <a name="details"></a><span data-ttu-id="7ff17-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7ff17-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ff17-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="7ff17-104">Product Name</span></span>|<span data-ttu-id="7ff17-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ff17-105">SQL Server</span></span>|  
|<span data-ttu-id="7ff17-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="7ff17-106">Event ID</span></span>|<span data-ttu-id="7ff17-107">33027</span><span class="sxs-lookup"><span data-stu-id="7ff17-107">33027</span></span>|  
|<span data-ttu-id="7ff17-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="7ff17-108">Event Source</span></span>|<span data-ttu-id="7ff17-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7ff17-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7ff17-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7ff17-110">Component</span></span>|<span data-ttu-id="7ff17-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7ff17-111">SQLEngine</span></span>|  
|<span data-ttu-id="7ff17-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="7ff17-112">Symbolic Name</span></span>|<span data-ttu-id="7ff17-113">SEC_CRYPTOPROV_CANTLOADDLL</span><span class="sxs-lookup"><span data-stu-id="7ff17-113">SEC_CRYPTOPROV_CANTLOADDLL</span></span>|  
|<span data-ttu-id="7ff17-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="7ff17-114">Message Text</span></span>|<span data-ttu-id="7ff17-115">Falha ao carregar o provedor criptográfico '%.\*ls' devido a uma assinatura inválida de Authenticode ou a um caminho de arquivo inválido.</span><span class="sxs-lookup"><span data-stu-id="7ff17-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span> <span data-ttu-id="7ff17-116">Verifique as mensagens anteriores à procura de outras falhas.</span><span class="sxs-lookup"><span data-stu-id="7ff17-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7ff17-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="7ff17-117">Explanation</span></span>  
 <span data-ttu-id="7ff17-118">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde usar o provedor criptográfico listado na mensagem de erro, porque o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde carregar a DLL.</span><span class="sxs-lookup"><span data-stu-id="7ff17-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to use the cryptographic provider listed in the error message, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not load the DLL.</span></span> <span data-ttu-id="7ff17-119">O nome é inválido ou a assinatura Authenticode é inválida.</span><span class="sxs-lookup"><span data-stu-id="7ff17-119">Either the name is invalid or the Authenticode signature is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ff17-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="7ff17-120">User Action</span></span>  
 <span data-ttu-id="7ff17-121">Verifique se o arquivo está presente e se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tem permissão para acessar o local.</span><span class="sxs-lookup"><span data-stu-id="7ff17-121">Check that the file is present and that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has permission to access that location.</span></span> <span data-ttu-id="7ff17-122">Verifique o log de erros à procura de mais mensagens relacionadas.</span><span class="sxs-lookup"><span data-stu-id="7ff17-122">Check the error log for additional related messages.</span></span> <span data-ttu-id="7ff17-123">Caso contrário, contate o provedor criptográfico para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7ff17-123">Otherwise, contact the cryptographic provider for more information.</span></span>  
  
  
