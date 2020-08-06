---
title: Programação do coletor de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- data collector [SQL Server], programming
ms.assetid: 53b4752b-055d-4716-b2bc-75b4cce84101
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9f4da839f25da8f8aab3e21fa98547eff72d2140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685916"
---
# <a name="data-collector-programming"></a><span data-ttu-id="54f76-102">Programação do coletor de dados</span><span class="sxs-lookup"><span data-stu-id="54f76-102">Data Collector Programming</span></span>
  <span data-ttu-id="54f76-103">A API do coletor de dados, no <xref:Microsoft.SqlServer.Management.Collector>, permite o controle programático de todas as operações de configuração por meio do modelo de objeto.</span><span class="sxs-lookup"><span data-stu-id="54f76-103">The data collector API, in <xref:Microsoft.SqlServer.Management.Collector>, allows programmatic control of all configuration operations through the object model.</span></span> <span data-ttu-id="54f76-104">Além disso, muitas das operações de coleta de dados que usam a API são implementadas como procedimentos armazenados instalados no servidor.</span><span class="sxs-lookup"><span data-stu-id="54f76-104">In addition, many of the data collection operations that use the API are implemented as stored procedures that are installed on the server.</span></span>

 <span data-ttu-id="54f76-105">A ilustração a seguir mostra os principais elementos do modelo de objeto do coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="54f76-105">The following illustration shows key elements of the data collector object model.</span></span>

 <span data-ttu-id="54f76-106">![O modelo de objeto Coletor de Dados](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "O modelo de objeto Coletor de Dados")</span><span class="sxs-lookup"><span data-stu-id="54f76-106">![The Data Collector Object Model](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "The Data Collector Object Model")</span></span>


