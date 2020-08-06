---
title: Definir inteligência de conta (Assistente de Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.mapaccounttype.f1
ms.assetid: fe4c204b-1031-4ac4-9916-8052ce2301cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17b8136e79097cd502d6b239ba6867c4e678c70f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679096"
---
# <a name="define-account-intelligence-business-intelligence-wizard"></a>Definir Inteligência de Conta (Assistente de Business Intelligence)
  Use a página **Definir Inteligência de Conta** para mapear tipos de conta definidos na instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] como tipos de conta definidos por uma tabela de origem na fonte de dados que fornece os dados para a dimensão de conta.  
  
> [!NOTE]  
>   Essa página será exibida se um atributo de dimensão tiver sido mapeado para o atributo **Tipo de Conta** na página **Configurar Atributos de Dimensão** .  
  
## <a name="options"></a>Opções  
 **Tipos de Conta de Tabela de Origem**  
 Exibe os valores contidos no atributo de dimensão atribuído ao atributo **Tipo de Conta** na página **Configurar Atributos de Dimensão** .  
  
 **Tipos de Conta Interna**  
 Selecione o tipo de conta definido na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que mapeia para os tipos de conta na tabela de origem.  
  
 A tabela a seguir lista os tipos de conta que estão definidos em uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .  
  
|Valor|Descrição|  
|-----------|-----------------|  
|**Ativo**|Valor de itens possuídos em um momento específico.|  
|**Saldo**|Contagem de algo em um momento específico.|  
|**Despesa**|Valor de despesas efetuadas.|  
|**Flow**|Contagem incremental de itens.|  
|**Líqui**|Valor de itens recebidos.|  
|**Dívida**|Valor de itens devidos em um momento específico.|  
|**Estatística**|Taxa calculada de algo ou contagem de algo que não agrega.|  
  
## <a name="see-also"></a>Consulte Também  
 [Ajuda F1 do assistente de Business Intelligence](business-intelligence-wizard-f1-help.md)   
 [O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md)   
 [O designer de dimensão &#40;Analysis Services de dados multidimensionais&#41;](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
