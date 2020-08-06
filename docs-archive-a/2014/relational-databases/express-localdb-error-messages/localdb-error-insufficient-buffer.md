---
title: LOCALDB_ERROR_INSUFFICIENT_BUFFER | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: ff67bda8-7e5c-4b06-8d7b-9985b6059a98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 934683cfca1a9a9c0596071824c21a0045e6ebab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583076"
---
# <a name="localdb_error_insufficient_buffer"></a><span data-ttu-id="15c93-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="15c93-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>
    
## <a name="details"></a><span data-ttu-id="15c93-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="15c93-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15c93-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="15c93-104">Product Name</span></span>|<span data-ttu-id="15c93-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="15c93-105">SQL Server</span></span>|  
|<span data-ttu-id="15c93-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="15c93-106">Event ID</span></span>|<span data-ttu-id="15c93-107">276</span><span class="sxs-lookup"><span data-stu-id="15c93-107">276</span></span>|  
|<span data-ttu-id="15c93-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="15c93-108">Event Source</span></span>|<span data-ttu-id="15c93-109">Runtime de banco de dados local do SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="15c93-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="15c93-110">Componente</span><span class="sxs-lookup"><span data-stu-id="15c93-110">Component</span></span>|<span data-ttu-id="15c93-111">API do runtime de banco de dados local</span><span class="sxs-lookup"><span data-stu-id="15c93-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="15c93-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="15c93-112">Message Text</span></span>|<span data-ttu-id="15c93-113">O buffer passado ao método de API da instância do Banco de Dados Local tem tamanho insuficiente.</span><span class="sxs-lookup"><span data-stu-id="15c93-113">The buffer passed to the Local Database instance API method has insufficient size.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="15c93-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="15c93-114">Explanation</span></span>  
 <span data-ttu-id="15c93-115">O buffer de entrada é muito curto e o truncamento não foi solicitado.</span><span class="sxs-lookup"><span data-stu-id="15c93-115">The input buffer is too short, and truncation was not requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="15c93-116">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="15c93-116">User Action</span></span>  
 <span data-ttu-id="15c93-117">Forneça um buffer do tamanho especificado.</span><span class="sxs-lookup"><span data-stu-id="15c93-117">Provide a buffer of the specified size.</span></span>  
  
  
