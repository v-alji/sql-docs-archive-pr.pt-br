---
title: Definir conversão de moeda (Assistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.existingscriptpage.f1
ms.assetid: 37dd65b7-9d8d-44ad-b316-96a92c622472
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1c60b6ad6964060164e273004f59604fef6574a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568874"
---
# <a name="define-currency-conversion-business-intelligence-wizard"></a>Definir Conversão de Moeda (Assistente de Business Intelligence)
  Use a página **Definir Conversão de Moeda** para examinar o script MDX que contém a funcionalidade de conversão de moeda gerada pelo Assistente de Business Intelligence. Em seguida, é possível usar esse script MDX gerado pelo assistente para substituir ou acrescentar a funcionalidade de conversão de moeda definida anteriormente no script MDX do cubo.  
  
> [!NOTE]  
>  Essa página será exibida apenas se o Assistente de Business Intelligence detectar pelo menos uma conversão de moeda definida anteriormente no script MDX do cubo. No script MDX de um cubo, conversões de moeda são enquadradas com os seguintes comentários:  
>   
>  `//<Currency conversion>`  
>   
>  `...`  
>   
>  `[MDX statements for the currency conversion]`  
>   
>  `...`  
>   
>  `//</Currency conversion>`  
>   
>  Se você alterar ou remover esses comentários, o Assistente de Business Intelligence poderá não ser capaz de detectar nenhuma conversão de moeda definida anteriormente.  
  
## <a name="options"></a>Opções  
 **Novo script de conversão de moeda**  
 Exibe o script MDX gerado pela sessão atual do Assistente de Business Intelligence.  
  
 **Substituir script de conversão de moeda existente**  
 Selecione para substituir o script MDX exibido em **Script de conversão de moeda existente** pelo script MDX exibido em **Novo script de conversão de moeda**.  
  
 **Anexar após**  
 Selecione para acrescentar o script MDX exibido em **Novo script de conversão de moeda** no final do script MDX exibido em **Script de conversão de moeda existente**. O script acrescentado é exibido como uma nova seção.  
  
 **Script de conversão de moeda existente**  
 Selecione a seção do script MDX existente que contém a funcionalidade de conversão de moeda definida anteriormente a ser substituída ou acrescentada.  
  
## <a name="see-also"></a>Consulte Também  
 [Ajuda F1 do assistente de Business Intelligence](business-intelligence-wizard-f1-help.md)   
 [O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md)   
 [O designer de dimensão &#40;Analysis Services de dados multidimensionais&#41;](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
