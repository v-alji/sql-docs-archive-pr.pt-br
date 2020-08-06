---
title: Especificando um eixo (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- XPath queries [SQLXML], location paths
- self axis
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- location path for XPath query
- axes [SQLXML]
ms.assetid: 65631795-3389-40cf-90ea-85e9438956c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e43281fe31d323a7eea19e749b80b59458752b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574588"
---
# <a name="specifying-an-axis-sqlxml-40"></a><span data-ttu-id="ad071-102">Especificando um eixo (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ad071-102">Specifying an Axis (SQLXML 4.0)</span></span>
    
-   <span data-ttu-id="ad071-103">O eixo especifica a relação de árvore entre os nós selecionados pela etapa de local e o nó de contexto.</span><span class="sxs-lookup"><span data-stu-id="ad071-103">The axis specifies the tree relationship between the nodes selected by the location step and the context node.</span></span> <span data-ttu-id="ad071-104">Há suporte para os seguintes eixos: `child`</span><span class="sxs-lookup"><span data-stu-id="ad071-104">The following axes are supported:  `child`</span></span>  
  
     <span data-ttu-id="ad071-105">Contém o filho do nó de contexto.</span><span class="sxs-lookup"><span data-stu-id="ad071-105">Contains the child of the context node.</span></span>  
  
     <span data-ttu-id="ad071-106">A seguinte expressão XPath (caminho de localização) seleciona a partir do nó de contexto atual todos os **\<Customer>** filhos:</span><span class="sxs-lookup"><span data-stu-id="ad071-106">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children:</span></span>  
  
    ```  
    child::Customer  
    ```  
  
     <span data-ttu-id="ad071-107">Na consulta XPath a seguir, `child` é o eixo.</span><span class="sxs-lookup"><span data-stu-id="ad071-107">In the following XPath query, `child` is the axis.</span></span> <span data-ttu-id="ad071-108">`Customer` é o teste de nó.</span><span class="sxs-lookup"><span data-stu-id="ad071-108">`Customer` is the node test.</span></span>  
  
-   `parent`  
  
     <span data-ttu-id="ad071-109">Contém o pai do nó de contexto.</span><span class="sxs-lookup"><span data-stu-id="ad071-109">Contains the parent of the context node.</span></span>  
  
     <span data-ttu-id="ad071-110">A expressão XPath a seguir seleciona todos os **\<Customer>** pais dos **\<Order>** filhos:</span><span class="sxs-lookup"><span data-stu-id="ad071-110">The following XPath expression selects all the **\<Customer>** parents of the **\<Order>** children:</span></span>  
  
    ```  
    child::Customer/child::Order[parent::Customer/@customerID="ALFKI"]  
    ```  
  
     <span data-ttu-id="ad071-111">Isso corresponde à especificação de `child::Customer`.</span><span class="sxs-lookup"><span data-stu-id="ad071-111">This is the same as specifying `child::Customer`.</span></span> <span data-ttu-id="ad071-112">Nesta consulta XPath, `child` e `parent` são os eixos.</span><span class="sxs-lookup"><span data-stu-id="ad071-112">In this XPath query, `child` and `parent` are the axes.</span></span> <span data-ttu-id="ad071-113">`Customer` e `Order` são os testes de nó.</span><span class="sxs-lookup"><span data-stu-id="ad071-113">`Customer` and `Order` are the node tests.</span></span>  
  
-   `attribute`  
  
     <span data-ttu-id="ad071-114">Contém o atributo do nó de contexto.</span><span class="sxs-lookup"><span data-stu-id="ad071-114">Contains the attribute of the context node.</span></span>  
  
     <span data-ttu-id="ad071-115">A expressão XPath a seguir seleciona o atributo **CustomerID** do nó de contexto:</span><span class="sxs-lookup"><span data-stu-id="ad071-115">The following XPath expression selects the **CustomerID** attribute of the context node:</span></span>  
  
    ```  
    attribute::CustomerID  
    ```  
  
-   `self`  
  
     <span data-ttu-id="ad071-116">Contém o próprio nó de contexto.</span><span class="sxs-lookup"><span data-stu-id="ad071-116">Contains the context node itself.</span></span>  
  
     <span data-ttu-id="ad071-117">A expressão XPath a seguir selecionará o nó atual se ele for o **\<Order>** nó:</span><span class="sxs-lookup"><span data-stu-id="ad071-117">The following XPath expression selects the current node if it is the **\<Order>** node:</span></span>  
  
    ```  
    self::Order  
    ```  
  
     <span data-ttu-id="ad071-118">Nesta consulta XPath, `self` é o eixo e `Order` é o teste de nó.</span><span class="sxs-lookup"><span data-stu-id="ad071-118">In this XPath query, `self` is the axis and `Order` is the node test.</span></span>  
  
  
