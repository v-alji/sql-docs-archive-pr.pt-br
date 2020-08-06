---
title: Cache pró-ativo (dimensões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- dimensions [Analysis Services], proactive caching
- proactive caching [Analysis Services]
ms.assetid: 7d57fe93-6e5f-4a50-844f-dd2bbdbb94a5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50c723d46b6c51fae0ccc227b5e58cf96f72c7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570310"
---
# <a name="proactive-caching-dimensions"></a><span data-ttu-id="a8c5d-102">Cache pró-ativo (dimensões)</span><span class="sxs-lookup"><span data-stu-id="a8c5d-102">Proactive Caching (Dimensions)</span></span>
  <span data-ttu-id="a8c5d-103">O cache pró-ativo fornece criação automática de cache MOLAP e gerenciamento de objetos OLAP.</span><span class="sxs-lookup"><span data-stu-id="a8c5d-103">Proactive caching provides automatic MOLAP cache creation and management for OLAP objects.</span></span> <span data-ttu-id="a8c5d-104">Os cubos incorporam imediatamente as alterações feitas nos dados no banco de dados, com base em modificações recebidas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a8c5d-104">The cubes immediately incorporate changes that are made to the data in the database, based upon notifications received from the database.</span></span> <span data-ttu-id="a8c5d-105">O objetivo do cache pró-ativo é oferecer o desempenho do MOLAP tradicional, além de manter a instantaneidade e facilidade de gerenciamento oferecida pelo ROLAP.</span><span class="sxs-lookup"><span data-stu-id="a8c5d-105">The goal of proactive caching is to provide the performance of traditional MOLAP, while retaining the immediacy and ease of management offered by ROLAP.</span></span>  
  
 <span data-ttu-id="a8c5d-106">Um objeto simples <xref:Microsoft.AnalysisServices.ProactiveCaching> é composto de: especificação de tempo e notificação de tabela.</span><span class="sxs-lookup"><span data-stu-id="a8c5d-106">A simple <xref:Microsoft.AnalysisServices.ProactiveCaching> object is composed of: timing specification, and table notification.</span></span> <span data-ttu-id="a8c5d-107">A especificação de tempo define o período de tempo para atualizar o cache depois que uma notificação de alteração for recebida.</span><span class="sxs-lookup"><span data-stu-id="a8c5d-107">The timing specification defines the timeframe for updating the cache after a change notification has been received.</span></span> <span data-ttu-id="a8c5d-108">A notificação de tabela define o esquema de notificação entre a tabela de dados e o objeto <xref:Microsoft.AnalysisServices.ProactiveCaching>.</span><span class="sxs-lookup"><span data-stu-id="a8c5d-108">The table notification defines the notification schema between the data table and the <xref:Microsoft.AnalysisServices.ProactiveCaching> object.</span></span>  
  
  
