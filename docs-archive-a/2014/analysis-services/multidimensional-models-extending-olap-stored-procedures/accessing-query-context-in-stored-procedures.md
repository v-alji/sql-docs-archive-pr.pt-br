---
title: Acessando o contexto de consulta em procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- execution context [Analysis Services]
- stored procedures [Analysis Services], query context
- Context object
- query context [Analysis Services]
ms.assetid: bdc7dad8-2f22-4265-aba4-a3a451527840
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9da8ddb223ed03c0208fe524ea5cd7195a039c97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678334"
---
# <a name="accessing-query-context-in-stored-procedures"></a><span data-ttu-id="dfdbd-102">Acessando o contexto de consulta nos procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="dfdbd-102">Accessing Query Context in Stored Procedures</span></span>
  <span data-ttu-id="dfdbd-103">O contexto de execução de um procedimento armazenado está disponível no código do procedimento armazenado como um objeto do `Context` do modelo de objeto de servidor do ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-103">The execution context of a stored procedure is available within the code of the stored procedure as the `Context` object of the ADOMD.NET server object model.</span></span> <span data-ttu-id="dfdbd-104">Trata-se de um contexto somente leitura e que não pode ser modificado pelo procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-104">This is a read-only context and cannot be modified by the stored procedure.</span></span> <span data-ttu-id="dfdbd-105">As propriedades a seguir estão disponíveis nesse objeto.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-105">The following properties are available on this object.</span></span>  
  
|<span data-ttu-id="dfdbd-106">Propriedade</span><span class="sxs-lookup"><span data-stu-id="dfdbd-106">Property</span></span>|<span data-ttu-id="dfdbd-107">Type</span><span class="sxs-lookup"><span data-stu-id="dfdbd-107">Type</span></span>|<span data-ttu-id="dfdbd-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="dfdbd-108">Description</span></span>|  
|--------------|----------|-----------------|  
|<span data-ttu-id="dfdbd-109">**CurrentCube**</span><span class="sxs-lookup"><span data-stu-id="dfdbd-109">**CurrentCube**</span></span>|<span data-ttu-id="dfdbd-110">Cubo</span><span class="sxs-lookup"><span data-stu-id="dfdbd-110">Cube</span></span>|<span data-ttu-id="dfdbd-111">O cubo do contexto de consulta atual.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-111">The cube for the current query context.</span></span>|  
|<span data-ttu-id="dfdbd-112">**CurrentDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="dfdbd-112">**CurrentDatabaseName**</span></span>|<span data-ttu-id="dfdbd-113">String</span><span class="sxs-lookup"><span data-stu-id="dfdbd-113">String</span></span>|<span data-ttu-id="dfdbd-114">O identificador do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-114">The identifier of the current database.</span></span>|  
|<span data-ttu-id="dfdbd-115">**CurrentConnection**</span><span class="sxs-lookup"><span data-stu-id="dfdbd-115">**CurrentConnection**</span></span>|<span data-ttu-id="dfdbd-116">Conexão</span><span class="sxs-lookup"><span data-stu-id="dfdbd-116">Connection</span></span>|<span data-ttu-id="dfdbd-117">Uma referência ao objeto de conexão no contexto atual.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-117">A reference to the connection object in the current context.</span></span>|  
|<span data-ttu-id="dfdbd-118">**Passar**</span><span class="sxs-lookup"><span data-stu-id="dfdbd-118">**Pass**</span></span>|<span data-ttu-id="dfdbd-119">Integer</span><span class="sxs-lookup"><span data-stu-id="dfdbd-119">Integer</span></span>|<span data-ttu-id="dfdbd-120">O número da passagem do contexto atual.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-120">The pass number for the current context.</span></span>|  
  
 <span data-ttu-id="dfdbd-121">Haverá um objeto `Context` quando o modelo de objeto de expressão MDX for usado em um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-121">The `Context` object exists when the Multidimensional Expressions (MDX) object model is used in a stored procedure.</span></span> <span data-ttu-id="dfdbd-122">Ele não estará disponível quando o modelo de objeto MDX for usado em um cliente.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-122">It is not available when the MDX object model is used on a client.</span></span> <span data-ttu-id="dfdbd-123">O objeto `Context` não é passado explicitamente para o procedimento armazenado nem retornado por ele.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-123">The `Context` object is not explicitly passed to or returned by the stored procedure.</span></span> <span data-ttu-id="dfdbd-124">Ele fica disponível durante a execução do procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="dfdbd-124">It is available during the execution of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfdbd-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dfdbd-125">See Also</span></span>  
 <span data-ttu-id="dfdbd-126">[Gerenciamento de assemblies de modelo multidimensional](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="dfdbd-126">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="dfdbd-127">Definindo procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="dfdbd-127">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
