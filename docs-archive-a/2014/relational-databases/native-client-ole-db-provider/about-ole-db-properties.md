---
title: Sobre propriedades OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, properties
- SQL Server Native Client OLE DB provider, properties
- properties [OLE DB]
- property values [SQL Server Native Client]
ms.assetid: 0b36a61e-b542-400d-a3d2-e6f643caf2c6
author: rothja
ms.author: jroth
ms.openlocfilehash: d4eb80ab9c0ab90da11d8580e9a2983455b676bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679930"
---
# <a name="about-ole-db-properties"></a><span data-ttu-id="7f737-102">Sobre propriedades OLE DB</span><span class="sxs-lookup"><span data-stu-id="7f737-102">About OLE DB Properties</span></span>
  <span data-ttu-id="7f737-103">Os consumidores definem valores de propriedade para solicitar um comportamento de objeto específico.</span><span class="sxs-lookup"><span data-stu-id="7f737-103">Consumers set property values to request specific object behavior.</span></span> <span data-ttu-id="7f737-104">Por exemplo, os consumidores usam propriedades para especificar as interfaces a serem expostas por um conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="7f737-104">For example, consumers use properties to specify the interfaces to be exposed by a rowset.</span></span> <span data-ttu-id="7f737-105">Eles obtêm os valores de propriedade para determinar os recursos de um objeto, como um conjunto de linhas, uma sessão ou um objeto de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7f737-105">Consumers get the property values to determine the capabilities of an object, such as a rowset, a session, or a data source object.</span></span>  
  
 <span data-ttu-id="7f737-106">Cada propriedade tem um valor, um tipo, uma descrição e um atributo de leitura/gravação e, no caso de propriedades de conjunto de linhas, um indicador que determina se ela pode ser aplicada por coluna.</span><span class="sxs-lookup"><span data-stu-id="7f737-106">Each property has a value, type, description, and read/write attribute, and for rowset properties, an indicator of whether it can be applied on a column-by-column basis.</span></span>  
  
 <span data-ttu-id="7f737-107">Uma propriedade é identificada por um GUID e um inteiro que representam a ID de propriedade.</span><span class="sxs-lookup"><span data-stu-id="7f737-107">A property is identified by a GUID and an integer representing the property ID.</span></span> <span data-ttu-id="7f737-108">Um conjunto de propriedades é um conjunto de todas as propriedades que compartilham o mesmo GUID.</span><span class="sxs-lookup"><span data-stu-id="7f737-108">A property set is a set of all properties that share the same GUID.</span></span> <span data-ttu-id="7f737-109">Além dos conjuntos de propriedades predefinidos OLE DB, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo implementa as propriedades e os conjuntos de propriedade específicos do provedor neles.</span><span class="sxs-lookup"><span data-stu-id="7f737-109">In addition to the predefined OLE DB property sets, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements provider-specific property sets and properties in them.</span></span> <span data-ttu-id="7f737-110">Cada propriedade pertence a um ou mais grupos de propriedades.</span><span class="sxs-lookup"><span data-stu-id="7f737-110">Each property belongs to one or more property groups.</span></span> <span data-ttu-id="7f737-111">Um grupo de propriedades é o grupo de todas as propriedades que se aplicam a um objeto específico.</span><span class="sxs-lookup"><span data-stu-id="7f737-111">A property group is the group of all properties that apply to a particular object.</span></span> <span data-ttu-id="7f737-112">Alguns grupos de propriedades incluem o grupo de propriedades de inicialização, o grupo de propriedades de fonte de dados, o grupo de propriedades de sessão, o grupo de propriedades de conjunto de linhas, o grupo de propriedades de tabela e o grupo de propriedades de coluna.</span><span class="sxs-lookup"><span data-stu-id="7f737-112">Some property groups include the initialization property group, data source property group, session property group, rowset property group, table property group, and column property group.</span></span> <span data-ttu-id="7f737-113">Há propriedades em cada um desses grupos de propriedade.</span><span class="sxs-lookup"><span data-stu-id="7f737-113">There are properties in each of these property groups.</span></span>  
  
 <span data-ttu-id="7f737-114">A definição dos valores de propriedade envolve:</span><span class="sxs-lookup"><span data-stu-id="7f737-114">Setting property values involves:</span></span>  
  
1.  <span data-ttu-id="7f737-115">Determinar as propriedades para as quais definir valores.</span><span class="sxs-lookup"><span data-stu-id="7f737-115">Determining the properties for which to set values.</span></span>  
  
2.  <span data-ttu-id="7f737-116">Determinar os conjuntos de propriedades que contêm as propriedades identificadas.</span><span class="sxs-lookup"><span data-stu-id="7f737-116">Determining the property sets that contain the identified properties.</span></span>  
  
3.  <span data-ttu-id="7f737-117">Alocar uma matriz de estruturas DBPROPSET, uma para cada conjunto de propriedades identificadas.</span><span class="sxs-lookup"><span data-stu-id="7f737-117">Allocating an array of DBPROPSET structures, one for each identified property set.</span></span>  
  
4.  <span data-ttu-id="7f737-118">Alocar uma matriz de estruturas DBPROP para cada conjunto de propriedades.</span><span class="sxs-lookup"><span data-stu-id="7f737-118">Allocating an array of DBPROP structures for each property set.</span></span> <span data-ttu-id="7f737-119">O número de elementos em cada matriz é o número de propriedades (identificadas na Etapa 1) que pertencem ao conjunto de propriedades.</span><span class="sxs-lookup"><span data-stu-id="7f737-119">The number of elements in each array is the number of properties (identified in Step 1) that belong to that property set.</span></span>  
  
5.  <span data-ttu-id="7f737-120">Preencher a estrutura DBPROP para cada propriedade.</span><span class="sxs-lookup"><span data-stu-id="7f737-120">Filling in the DBPROP structure for each property.</span></span>  
  
6.  <span data-ttu-id="7f737-121">Preencher as informações (GUID do conjunto de propriedades, contagem do número de elementos e um ponteiro para a matriz DBPROP correspondente) na estrutura DBPROPSET para cada conjunto de propriedades.</span><span class="sxs-lookup"><span data-stu-id="7f737-121">Filling in information (property set GUID, count of number of elements, and a pointer to the corresponding DBPROP array) in the DBPROPSET structure for each property set.</span></span>  
  
7.  <span data-ttu-id="7f737-122">Chamar um método para definir propriedades e passar a contagem e a matriz de estruturas DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="7f737-122">Calling a method to set properties and passing the count and the array of DBPROPSET structures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f737-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f737-123">See Also</span></span>  
 <span data-ttu-id="7f737-124">[Criando um aplicativo de provedor de OLE DB de SQL Server Native Client](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="7f737-124">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="7f737-125">Propriedades (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7f737-125">Properties (OLE DB)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112207)  
  
  
