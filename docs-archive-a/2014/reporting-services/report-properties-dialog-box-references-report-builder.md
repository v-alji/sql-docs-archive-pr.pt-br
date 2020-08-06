---
title: Caixa de diálogo Propriedades do relatório, referências (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c28e9053a1c13f8d0e0b7b44f3b1a037976c318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681401"
---
# <a name="report-properties-dialog-box-references-report-builder"></a>Caixa de diálogo Propriedades do Relatório, Referências (Construtor de Relatórios)
  Selecione **Referências** na caixa de diálogo **Propriedades do Relatório** para adicionar ou remover as referências para assemblies personalizados ou outros assemblies externos e instâncias de classe personalizada usadas pelas expressões na definição do relatório. Assemblies personalizados não têm suporte no modo local no Construtor de Relatórios. Para criar relatórios que usam assemblies personalizados, use Report Designer no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .  
  
## <a name="options"></a>Opções  
 **Adicionar ou remover assemblies**  
 Lista os assemblies aos quais o relatório faz referência. O assembly deve estar disponível no computador no qual a ferramenta que você usando para criar o relatório está instalada e no servidor de relatório. O nome da referência deve corresponder exatamente ao conteúdo das **\<CodeModule>** marcas no arquivo de linguagem de definição de relatório (. RDL).  
  
 **Adicionar**  
 Clique para adicionar um assembly. Clique no botão de reticências (...) para abrir a caixa de diálogo **abrir** e selecione os assemblies necessários para concluir o processamento do relatório e a avaliação da expressão.  
  
 **Remover**  
 Para remover uma referência de assembly da lista, selecione o nome do assembly e clique no botão **Remover** .  
  
 **Adicionar ou remover classes**  
 Lista as instâncias de classe usadas pelo relatório. A lista de classe só é usada por membros baseados em instância, não membros estáticos.  
  
 **Adicionar**  
 Clique para adicionar uma referência de classe. Clique no botão de reticências (...) para abrir a caixa de diálogo **abrir** e selecione as classes necessárias para concluir o processamento do relatório e a avaliação da expressão.  
  
 **Remover**  
 Para excluir a instância de classe, selecione-a e clique no botão **Remover** .  
  
 **Limpeza**  
 Para classes que têm dependências, você pode mover esta referência mais para cima na lista.  
  
 **Down**  
 Para classes que têm dependências, você pode mover esta referência mais para baixo na lista.  
  
## <a name="see-also"></a>Consulte Também  
 [Construtor de Relatórios ajuda para caixas de diálogo, painéis e assistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [Expressões &#40;Construtor de Relatórios e SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md)  
  
  
