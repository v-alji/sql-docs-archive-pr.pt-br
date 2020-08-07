---
title: Remover UDT&#39;s nomeados após os tipos de dados de data e hora reservados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- time data type [SQL Server], UDTs
- date data type [SQL Server], UDTs
ms.assetid: 48f109af-b1d1-4f03-a7e3-8a0b05ed94e8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 827f060b309a7a620fd448554b074f45d78d3cb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576148"
---
# <a name="remove-udt39s-named-after-the-reserved-date-and-time-data-types"></a><span data-ttu-id="adaf7-102">Remover UDT&#39;s nomeados após os tipos de dados de data e hora reservados</span><span class="sxs-lookup"><span data-stu-id="adaf7-102">Remove UDT&#39;s named after the reserved DATE and TIME data types</span></span>
  <span data-ttu-id="adaf7-103">O Supervisor de Atualização detectou um tipo definido pelo usuário (UDT) que tem o mesmo nome de um termo reservado para os tipos de dados `date` ou `time`.</span><span class="sxs-lookup"><span data-stu-id="adaf7-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for either the `date` or the `time` data types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="adaf7-104">Componente</span><span class="sxs-lookup"><span data-stu-id="adaf7-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="adaf7-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="adaf7-105">Description</span></span>  
 <span data-ttu-id="adaf7-106">Os termos usados para tipos de dados não devem ser utilizados como nomes de UDTs de alias ou CLR.</span><span class="sxs-lookup"><span data-stu-id="adaf7-106">The terms used for data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="adaf7-107">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="adaf7-107">Corrective Action</span></span>  
 <span data-ttu-id="adaf7-108">Remova o UDT que tem o mesmo nome do tipo de dados e recrie o UDT com um nome não reservado.</span><span class="sxs-lookup"><span data-stu-id="adaf7-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
  
