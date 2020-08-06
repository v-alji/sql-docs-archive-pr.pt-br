---
title: Remover UDTs nomeados após os tipos de dados reservados GEOMETRY e geography | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], UDTs
- geography data type [SQL Server], UDTs
ms.assetid: a167ce3a-50b4-4e77-a884-adb23b586c72
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4977d45d53e1114edc8e04ad504963bae0b9eb9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686046"
---
# <a name="remove-udts-named-after-the-reserved-geometry-and-geography-data-types"></a><span data-ttu-id="22e1b-102">Remover UDTs com o mesmo nome dos tipos de dados reservados GEOMETRY e GEOGRAPHY</span><span class="sxs-lookup"><span data-stu-id="22e1b-102">Remove UDTs named after the reserved GEOMETRY and GEOGRAPHY data types</span></span>
  <span data-ttu-id="22e1b-103">O Supervisor de Atualização detectou um tipo definido pelo usuário (UDT) que tem o mesmo nome de um termo reservado para os tipos de dados `geometry` ou `geography`.</span><span class="sxs-lookup"><span data-stu-id="22e1b-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for either the `geometry` or the `geography` data types.</span></span> <span data-ttu-id="22e1b-104">Os tipos de dados `geometry` e `geography` fazem parte do recurso de dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="22e1b-104">The `geometry` and `geography` data types are part of the spatial data feature.</span></span>  
  
## <a name="component"></a><span data-ttu-id="22e1b-105">Componente</span><span class="sxs-lookup"><span data-stu-id="22e1b-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="22e1b-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="22e1b-106">Description</span></span>  
 <span data-ttu-id="22e1b-107">Os termos usados para tipos de dados espaciais não devem ser utilizados como nomes de UDTs de alias ou CLR.</span><span class="sxs-lookup"><span data-stu-id="22e1b-107">The terms used for spatial data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="22e1b-108">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="22e1b-108">Corrective Action</span></span>  
 <span data-ttu-id="22e1b-109">Remova o UDT que tem o mesmo nome do tipo de dados e recrie o UDT com um nome não reservado.</span><span class="sxs-lookup"><span data-stu-id="22e1b-109">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="22e1b-110">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="22e1b-110">External Resources</span></span>  
 [<span data-ttu-id="22e1b-111">Criando um tipo definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="22e1b-111">Creating a User-Defined Type</span></span>](../../relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types.md)  
  
 [<span data-ttu-id="22e1b-112">Visão geral de tipos de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="22e1b-112">Spatial Data Types Overview</span></span>](../../relational-databases/spatial/spatial-data-types-overview.md)  
  
  
