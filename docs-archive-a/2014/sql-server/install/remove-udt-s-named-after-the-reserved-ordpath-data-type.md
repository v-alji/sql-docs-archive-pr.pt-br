---
title: Remover UDT&#39;s nomeados após o tipo de dados ORDPATH reservado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 474e910a-6abb-4e28-acc2-055338c011d4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0528d19de17781d863e3a42fdef7db558fe5d190
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686047"
---
# <a name="remove-udt39s-named-after-the-reserved-ordpath-data-type"></a><span data-ttu-id="6488d-102">Remover UDT&#39;s nomeados após o tipo de dados ORDPATH reservado</span><span class="sxs-lookup"><span data-stu-id="6488d-102">Remove UDT&#39;s named after the reserved ORDPATH data type</span></span>
  <span data-ttu-id="6488d-103">O Supervisor de Atualização detectou um tipo definido pelo usuário (UDT) que tem o mesmo nome de um termo reservado para o tipo de dados `ORDPATH`.</span><span class="sxs-lookup"><span data-stu-id="6488d-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for the `ORDPATH` data type.</span></span>  
  
## <a name="component"></a><span data-ttu-id="6488d-104">Componente</span><span class="sxs-lookup"><span data-stu-id="6488d-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="6488d-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="6488d-105">Description</span></span>  
 <span data-ttu-id="6488d-106">Os termos usados para tipos de dados internos não devem ser utilizados como nomes de UDTs de alias ou CLR.</span><span class="sxs-lookup"><span data-stu-id="6488d-106">The terms used for built-in data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="6488d-107">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="6488d-107">Corrective Action</span></span>  
 <span data-ttu-id="6488d-108">Remova o UDT que tem o mesmo nome do tipo de dados e recrie o UDT com um nome não reservado.</span><span class="sxs-lookup"><span data-stu-id="6488d-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="6488d-109">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="6488d-109">External Resources</span></span>  
 [<span data-ttu-id="6488d-110">Criando um tipo definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="6488d-110">Creating a User-Defined Type</span></span>](../../relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types.md)  
  
  
