---
title: ISSCommandWithParameters (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSCommandWithParameters interface
ms.assetid: 3419b7f3-36a3-4863-816e-e641e4e90496
author: rothja
ms.author: jroth
ms.openlocfilehash: 295026497a97b4ce13d1a1a68de48079809390ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572042"
---
# <a name="isscommandwithparameters-ole-db"></a><span data-ttu-id="6c8f5-102">ISSCommandWithParameters (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="6c8f5-102">ISSCommandWithParameters (OLE DB)</span></span>
  <span data-ttu-id="6c8f5-103">**ISSCommandWithParameters** dá suporte a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML e UDTs (tipos definidos pelo usuário).</span><span class="sxs-lookup"><span data-stu-id="6c8f5-103">**ISSCommandWithParameters** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML and user-defined types (UDT).</span></span> <span data-ttu-id="6c8f5-104">Esta é uma interface opcional que herda da interface OLE DB principal **ICommandWithParameters**.</span><span class="sxs-lookup"><span data-stu-id="6c8f5-104">This is an optional interface that inherits from the core OLE DB interface **ICommandWithParameters**.</span></span> <span data-ttu-id="6c8f5-105">Além dos três métodos herdados de **ICommandWithParameters**; **GetParameterInfo**, **MapParameterNames**e **SetParameterInfo**; **ISSCommandWithParameters** fornece dois novos métodos usados para identificar os tipos de dados específicas de servidor.</span><span class="sxs-lookup"><span data-stu-id="6c8f5-105">In addition to the three methods inherited from **ICommandWithParameters**; **GetParameterInfo**, **MapParameterNames**, and **SetParameterInfo**; **ISSCommandWithParameters** provides two new methods that are used to handle server specific data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c8f5-106"> A interface **ISSCommandWithParameters** pode ser usada quando são usados Componentes de Serviço, mas os próprios Componentes de Serviço não usarão esta interface.</span><span class="sxs-lookup"><span data-stu-id="6c8f5-106">The **ISSCommandWithParameters** interface can be used when Service Components are used, but the Service Components themselves will not use this interface.</span></span>  
  
|<span data-ttu-id="6c8f5-107">Método</span><span class="sxs-lookup"><span data-stu-id="6c8f5-107">Method</span></span>|<span data-ttu-id="6c8f5-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="6c8f5-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6c8f5-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8f5-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-getparameterproperties-ole-db.md)|<span data-ttu-id="6c8f5-110">Retorna uma estrutura de conjunto de propriedades **SSPARAMPROPS** na matriz para cada parâmetro UDT ou XML passado ao comando, mas nenhum é retornado para os outros tipos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="6c8f5-110">Returns one **SSPARAMPROPS** property set structure in the array for each UDT or XML parameter passed to the command, but none is returned for other types of parameters.</span></span>|  
|[<span data-ttu-id="6c8f5-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8f5-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-setparameterproperties-ole-db.md)|<span data-ttu-id="6c8f5-112">Define as propriedades de parâmetro por parâmetro por ordinal ou define as propriedades de parâmetro em massa, especificando uma matriz de estruturas **SSPARAMPROPS** .</span><span class="sxs-lookup"><span data-stu-id="6c8f5-112">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of **SSPARAMPROPS** structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c8f5-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6c8f5-113">See Also</span></span>  
 <span data-ttu-id="6c8f5-114">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="6c8f5-114">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="6c8f5-115">[Usando tipos de dados XML](../native-client/features/using-xml-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="6c8f5-115">[Using XML Data Types](../native-client/features/using-xml-data-types.md) </span></span>  
 [<span data-ttu-id="6c8f5-116">Usando tipos definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="6c8f5-116">Using User-Defined Types</span></span>](../native-client/features/using-user-defined-types.md)  
  
  
