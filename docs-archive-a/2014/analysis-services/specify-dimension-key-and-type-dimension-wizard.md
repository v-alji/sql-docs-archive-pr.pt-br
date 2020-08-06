---
title: Especificar chave e tipo de dimensão (Assistente para dimensões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionkeyandtype.f1
ms.assetid: d7d5db55-36c3-45f6-ade3-29aa516589c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc08584ed12de8597b8289fd223cc47945d7d087
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581510"
---
# <a name="specify-dimension-key-and-type-dimension-wizard"></a>Especificar Chave e Tipo de Dimensão (Assistente para Dimensões)
  Use a página **Especificar Chave e Tipo de Dimensão** para definir o atributo de chave da dimensão e indicar se a dimensão é uma SCD (dimensão de alteração lenta).  
  
> [!NOTE]  
>  Essa página será exibida apenas se você tiver selecionado **Criar a dimensão sem usar uma fonte de dados** na página **Selecionar Método de Criação** e **Dimensão padrão** na página **Selecionar o Tipo de Dimensão** .  
  
## <a name="options"></a>Opções  
 **Atributo de chave**  
 Selecione o atributo que será o atributo de chave da dimensão.  
  
> [!NOTE]  
>  Se nenhum atributo tiver sido definido para a dimensão, o único valor disponível para essa opção será **Criar atributo de chave automaticamente**. Esse valor não estará disponível se qualquer atributo estiver definido para a dimensão.  
  
 **Esta é uma dimensão variável**  
 Selecione para indicar que a dimensão é uma dimensão de alteração lenta. A seleção dessa opção criará colunas e atributos adicionais que podem ser usados para acompanhar o movimento de membros dentro das hierarquias da dimensão ao longo do tempo.  
  
## <a name="see-also"></a>Consulte Também  
 [Ajuda F1 do assistente para dimensões](dimension-wizard-f1-help.md)   
 [Dimensões &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)   
 [Dimensões em modelos multidimensionais](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
