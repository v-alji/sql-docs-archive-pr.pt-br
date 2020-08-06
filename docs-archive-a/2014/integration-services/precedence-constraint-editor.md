---
title: Editor de restrição de precedência | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.precedenceconstraint.f1
helpviewer_keywords:
- Precedence Constraint Editor dialog box
ms.assetid: b10d4330-6e35-4037-b309-ef56efcd60c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6853d1974f4276361d60e1d73b34c72a366a7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571429"
---
# <a name="precedence-constraint-editor"></a>Editor de Restrição de Precedência
  Use a caixa de diálogo **Editor de Restrição de Precedência** para configurar as restrições de precedência.  
  
## <a name="options"></a>Opções  
 **Operação de avaliação**  
 Especifica a operação de avaliação usada pela restrição de precedência. As operações são: **Constraint**, **Expression**, **Expression and Constraint** e **Expression or Constraint**.  
  
 **Valor**  
 Especifique o valor de restrição: **Success**, **Failure** ou **Completion**.  
  
> [!NOTE]  
>   A linha de restrição de precedência é verde para **Success**, realçado para **Failure**e azul para **Completion**.  
  
 **Expression**  
 Se usar as operações **Expressão**, **Expressão e Restrição**ou **Expressão ou Restrição**, digite uma expressão ou inicie o Construtor de Expressões para criar a expressão. A expressão deve ser avaliada como um booliano.  
  
 **Test**  
 Valide a expressão.  
  
 **AND lógico**  
 Selecione para especificar que várias restrições de precedência no mesmo executável devem ser avaliadas juntas. Todas as restrições devem ser avaliadas como `True`.  
  
> [!NOTE]  
>  Este tipo de restrição de precedência aparece como uma linha sólida nas cores verde, realçado ou azul.  
  
 **OR lógico**  
 Selecione para especificar que várias restrições de precedência no mesmo executável devem ser avaliadas juntas. Pelo menos uma restrição deve ser avaliada como `True`.  
  
> [!NOTE]  
>  Este tipo de restrição de precedência aparece como uma linha pontilhada nas cores verde, realçado ou azul.  
  
## <a name="see-also"></a>Consulte Também  
 [Restrições de precedência](control-flow/precedence-constraints.md)   
 [Tarefas do Integration Services](control-flow/integration-services-tasks.md)   
 [Contêineres de Integration Services](control-flow/integration-services-containers.md)   
 [Expressões do SSIS &#40;Integration Services&#41;](expressions/integration-services-ssis-expressions.md)  
  
  
