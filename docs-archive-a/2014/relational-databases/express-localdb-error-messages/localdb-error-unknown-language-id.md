---
title: LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: fa082dca-bf88-46e7-b61e-7ac8835a3493
author: stevestein
ms.author: sstein
ms.openlocfilehash: e71f7b443a1999a5edbb17dc11ee4d578834faf4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575130"
---
# <a name="localdb_error_unknown_language_id"></a><span data-ttu-id="679bb-102">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span><span class="sxs-lookup"><span data-stu-id="679bb-102">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span></span>
    
## <a name="details"></a><span data-ttu-id="679bb-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="679bb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="679bb-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="679bb-104">Product Name</span></span>|<span data-ttu-id="679bb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="679bb-105">SQL Server</span></span>|  
|<span data-ttu-id="679bb-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="679bb-106">Event ID</span></span>|<span data-ttu-id="679bb-107">270</span><span class="sxs-lookup"><span data-stu-id="679bb-107">270</span></span>|  
|<span data-ttu-id="679bb-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="679bb-108">Event Source</span></span>|<span data-ttu-id="679bb-109">Runtime de banco de dados local do SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="679bb-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="679bb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="679bb-110">Component</span></span>|<span data-ttu-id="679bb-111">API do runtime de banco de dados local</span><span class="sxs-lookup"><span data-stu-id="679bb-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="679bb-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="679bb-112">Message Text</span></span>|<span data-ttu-id="679bb-113">Erro ao obter a mensagem de erro localizada:</span><span class="sxs-lookup"><span data-stu-id="679bb-113">Error getting the localized error message.</span></span> <span data-ttu-id="679bb-114">O idioma especificado pelo parâmetro 'ID do idioma' é desconhecido.</span><span class="sxs-lookup"><span data-stu-id="679bb-114">The language specified by 'Language ID' parameter is unknown.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="679bb-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="679bb-115">Explanation</span></span>  
 <span data-ttu-id="679bb-116">O idioma solicitado para a mensagem de erro de Runtime do Banco de Dados Local é desconhecido ou não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="679bb-116">The requested language for the Local Database Runtime error message is unknown or not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="679bb-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="679bb-117">User Action</span></span>  
 <span data-ttu-id="679bb-118">Tente solicitar um dos idiomas com suporte para mensagens de erro de Runtime de Banco de Dados Local ou um idioma padrão.</span><span class="sxs-lookup"><span data-stu-id="679bb-118">Try requesting one of the supported languages for Local Database Runtime error messages, or a default language.</span></span>  
  
  
