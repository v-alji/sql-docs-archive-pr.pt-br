---
title: Definir uma relação de fatos e as propriedades da relação de fatos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact dimensions [Analysis Services]
ms.assetid: d8e41724-da77-4ac1-bc42-956b5d91ea5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 15f67a4bdf699bbc6443fc76ce54bcfb35831827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680101"
---
# <a name="define-a-fact-relationship-and-fact-relationship-properties"></a><span data-ttu-id="95846-102">Definir uma relação de fato e propriedades de relação de fato</span><span class="sxs-lookup"><span data-stu-id="95846-102">Define a Fact Relationship and Fact Relationship Properties</span></span>
  <span data-ttu-id="95846-103">Quando você definir uma nova dimensão de cubo ou um novo grupo de medidas, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tentará detectar se existe uma relação de fatos e, em seguida, definirá o uso da dimensão como `Fact`.</span><span class="sxs-lookup"><span data-stu-id="95846-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a fact dimension relationship exists and then set the dimension usage setting to `Fact`.</span></span> <span data-ttu-id="95846-104">É possível exibir ou editar uma relação de dimensão de fatos na guia **Uso da Dimensão** do Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="95846-104">You can view or edit a fact dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="95846-105">A relação de dimensão de fatos entre uma dimensão e um grupo de medidas apresenta as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="95846-105">The fact relationship between a dimension and a measure group has the following constraints:</span></span>  
  
-   <span data-ttu-id="95846-106">Uma dimensão de cubo pode ter apenas uma relação de fatos com um determinado grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="95846-106">A cube dimension can have only one fact relationship to a particular measure group.</span></span>  
  
-   <span data-ttu-id="95846-107">Uma dimensão de cubo pode ter relações de fatos separadas com vários grupos de medidas.</span><span class="sxs-lookup"><span data-stu-id="95846-107">A cube dimension can have separate fact relationships to multiple measure groups.</span></span>  
  
-   <span data-ttu-id="95846-108">O atributo de granularidade da relação deve ser o atributo de chave (como Número da Transação) da dimensão.</span><span class="sxs-lookup"><span data-stu-id="95846-108">The granularity attribute for the relationship must be the key attribute (such as Transaction Number) for the dimension.</span></span> <span data-ttu-id="95846-109">Isso cria uma relação de um para um entre a dimensão e os fatos da tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="95846-109">This creates a one-to-one relationship between the dimension and facts in the fact table.</span></span>  
  
  
