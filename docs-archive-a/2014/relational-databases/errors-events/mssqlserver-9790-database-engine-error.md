---
title: MSSQLSERVER_9790 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9790 (Database Engine error)
ms.assetid: 83fd379f-5deb-4f97-8cb4-282e3d3fed94
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d6d065d4a0e841da3b5ecb84f902df17dcfd60c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573037"
---
# <a name="mssqlserver_9790"></a><span data-ttu-id="4cb38-102">MSSQLSERVER_9790</span><span class="sxs-lookup"><span data-stu-id="4cb38-102">MSSQLSERVER_9790</span></span>
    
## <a name="details"></a><span data-ttu-id="4cb38-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4cb38-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4cb38-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="4cb38-104">Product Name</span></span>|<span data-ttu-id="4cb38-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4cb38-105">SQL Server</span></span>|  
|<span data-ttu-id="4cb38-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4cb38-106">Event ID</span></span>|<span data-ttu-id="4cb38-107">9790</span><span class="sxs-lookup"><span data-stu-id="4cb38-107">9790</span></span>|  
|<span data-ttu-id="4cb38-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="4cb38-108">Event Source</span></span>|<span data-ttu-id="4cb38-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4cb38-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4cb38-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4cb38-110">Component</span></span>|<span data-ttu-id="4cb38-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4cb38-111">SQLEngine</span></span>|  
|<span data-ttu-id="4cb38-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="4cb38-112">Symbolic Name</span></span>|<span data-ttu-id="4cb38-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span><span class="sxs-lookup"><span data-stu-id="4cb38-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span></span>|  
|<span data-ttu-id="4cb38-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="4cb38-114">Message Text</span></span>|<span data-ttu-id="4cb38-115">Não é possível rotear a mensagem de entrada.</span><span class="sxs-lookup"><span data-stu-id="4cb38-115">Unable to route the incoming message.</span></span> <span data-ttu-id="4cb38-116">O banco de dados de sistema MSDB que contém informações de roteamento está no modo SINGLE USER.</span><span class="sxs-lookup"><span data-stu-id="4cb38-116">The system database MSDB containing routing information is in SINGLE USER mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4cb38-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="4cb38-117">Explanation</span></span>  
 <span data-ttu-id="4cb38-118">Ocorreu um erro ao tentar classificar uma mensagem recebida sem-cabo porque o banco de dados MSDB estava no modo usuário único.</span><span class="sxs-lookup"><span data-stu-id="4cb38-118">An error occurred while trying to classify a message received off the wire because the MSDB database was in Single User mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4cb38-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="4cb38-119">User Action</span></span>  
 <span data-ttu-id="4cb38-120">Altere o MSDB para o modo MULTI USER com o comando ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="4cb38-120">Change MSDB to be in MULTI USER mode with the ALTER DATABASE command.</span></span>  
  
  
