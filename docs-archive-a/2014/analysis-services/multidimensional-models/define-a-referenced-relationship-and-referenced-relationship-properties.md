---
title: Definir uma relação referenciada e propriedades de relação referenciadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- referenced dimension relationship
- relationships [Analysis Services], referenced dimensions
ms.assetid: 5bb44b41-635b-4398-8fe9-0bfbb142553e
author: minewiskan
ms.author: owend
ms.openlocfilehash: a84cf2ed95ab3660c5a6b3c039dc58351dc43264
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680680"
---
# <a name="define-a-referenced-relationship-and-referenced-relationship-properties"></a><span data-ttu-id="4b328-102">Definir uma relação referenciada e as propriedades da relação referenciada</span><span class="sxs-lookup"><span data-stu-id="4b328-102">Define a Referenced Relationship and Referenced Relationship Properties</span></span>
  <span data-ttu-id="4b328-103">Uma relação de dimensão de referência é definida na guia **Uso da Dimensão** do Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="4b328-103">A reference dimension relationship is defined on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="4b328-104">A relação de dimensão de referência é definida especificando-se o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4b328-104">The reference dimension relationship is defined by specifying the following:</span></span>  
  
-   <span data-ttu-id="4b328-105">A dimensão intermediária à qual se unir.</span><span class="sxs-lookup"><span data-stu-id="4b328-105">The intermediate dimension to which to join.</span></span> <span data-ttu-id="4b328-106">Pode ser uma dimensão regular ou outra dimensão de referência.</span><span class="sxs-lookup"><span data-stu-id="4b328-106">This can be a regular dimension or another reference dimension.</span></span>  
  
-   <span data-ttu-id="4b328-107">Um atributo da dimensão de referência que define o nível mais baixo para o qual a dimensão está disponível para agregação com relação ao grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="4b328-107">A reference dimension attribute that defines the lowest level that the dimension is available for aggregation with regard to the measure group.</span></span>  
  
-   <span data-ttu-id="4b328-108">O atributo (chave estrangeira) da dimensão intermediária que corresponde ao atributo da dimensão de referência.</span><span class="sxs-lookup"><span data-stu-id="4b328-108">The (foreign key) attribute in the intermediate dimension that corresponds to the reference dimension attribute.</span></span>  
  
 <span data-ttu-id="4b328-109">Observe que a coluna que vincula a dimensão de referência à tabela de fatos, que geralmente é o atributo principal da dimensão de referência, também deve ser definida como um atributo da dimensão intermediária.</span><span class="sxs-lookup"><span data-stu-id="4b328-109">Notice that the column that links the reference dimension to the fact table, which is generally the key attribute in the reference dimension, must also be defined as an attribute in the intermediate dimension.</span></span> <span data-ttu-id="4b328-110">Ao criar uma cadeia de dimensões de referência, comece criando a relação regular entre a primeira dimensão da cadeia e o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="4b328-110">When you create a chain of reference dimensions, start by creating the regular relationship between the first dimension in the chain and the measure group.</span></span> <span data-ttu-id="4b328-111">Em seguida, crie cada relação de referência adicional na ordem.</span><span class="sxs-lookup"><span data-stu-id="4b328-111">Then create each additional referenced relationship in order.</span></span> <span data-ttu-id="4b328-112">A relação de referência pode ser criada apenas para uma dimensão que possui uma relação com o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="4b328-112">A referenced relationship can only be made to a dimension that has an existing relationship to the measure group.</span></span>  
  
 <span data-ttu-id="4b328-113">Quando você cria uma relação de dimensão de referência, o vínculo do atributo da dimensão é materializado por padrão.</span><span class="sxs-lookup"><span data-stu-id="4b328-113">When you create a reference dimension relationship, the dimension attribute link is materialized by default.</span></span> <span data-ttu-id="4b328-114">A materialização do atributo da dimensão faz com que o valor do vínculo entre a tabela de fatos e a dimensão de referência de cada linha seja materializado, ou armazenado, na estrutura MOLAP da dimensão durante o processamento.</span><span class="sxs-lookup"><span data-stu-id="4b328-114">Materializing a dimension attribute link causes the value of the link between the fact table and the reference dimension for each row to be materialized, or stored, in the MOLAP structure for the dimension during processing.</span></span> <span data-ttu-id="4b328-115">Isso terá um efeito secundário no desempenho do processamento e nos requisitos de armazenamento, mas melhorará o desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="4b328-115">This will have a minor effect on processing performance and storage requirements, but will improve query performance.</span></span>  
  
 <span data-ttu-id="4b328-116">Em uma dimensão de referência, a granularidade é especificada pela identificação do atributo que define a relação entre uma dimensão de referência e o grupo de medidas correspondente à tabela principal da dimensão.</span><span class="sxs-lookup"><span data-stu-id="4b328-116">In a reference dimension, granularity is specified by identifying the attribute that defines the relationship between a reference dimension and the measure group corresponding to the main table of the dimension.</span></span> <span data-ttu-id="4b328-117">Quando várias dimensões de referência são encadeadas, as referências definem a relação entre a dimensão externa e o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="4b328-117">When multiple reference dimensions are chained together, the references define the relationship from the outermost dimension to the measure group.</span></span>  
  
  
