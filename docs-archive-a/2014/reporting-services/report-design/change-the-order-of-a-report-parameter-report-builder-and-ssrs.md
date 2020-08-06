---
title: Alterar a ordem de um parâmetro de relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: abd61e19-dba3-423c-a26c-e8bc43197d3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad9dd25be7a87fee089a48849fcc716e682e4c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684065"
---
# <a name="change-the-order-of-a-report-parameter-report-builder-and-ssrs"></a>Alterar a ordem de um parâmetro de relatório (Construtor de Relatórios e SSRS)
  Altere a ordem dos parâmetros de relatório quando você tiver um parâmetro dependente que tenha sido listado antes de o parâmetro ser dependente. A ordem do parâmetro é importante quando você tem parâmetros em cascata ou quando você deseja mostrar aos usuários o valor padrão de um parâmetro antes que eles escolham os valores para outros parâmetros. Um parâmetro de relatório dependente contém uma referência, seja a consulta de valores padrão ou na consulta de valores válidos, a um parâmetro de consulta que aponta para um parâmetro de relatório que está depois dele na lista de parâmetros no painel de dados do relatório.  
  
 A ordem em que você vê os parâmetros exibidos na barra de ferramentas do visualizador de relatórios é determinada pela ordem dos parâmetros no painel de dados do relatório.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-order-of-report-parameters"></a>Para alterar a ordem dos parâmetros de relatório  
  
1.  No painel de dados do relatório, expanda o nó Parâmetros.  
  
2.  Clique em um parâmetro e use os botões de seta para cima e para baixo da barra de ferramentas do painel de dados do relatório para movê-lo para cima ou para baixo na lista. A imagem a seguir mostra o painel Dados do Relatório no Construtor de Relatórios.  
  
     ![painel Dados do Relatório](../media/reportdatapane.png "painel Dados do Relatório")  
  
## <a name="see-also"></a>Consulte Também  
 [Parâmetros de relatório &#40;Construtor de Relatórios e Report Designer&#41;](report-parameters-report-builder-and-report-designer.md)   
 [Construtor de Relatórios ajuda para caixas de diálogo, painéis e assistentes](../report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [Adicionar parâmetros em cascata a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)   
 [Tutorial: adicionar um parâmetro ao seu relatório &#40;Construtor de Relatórios&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md)   
 [Adicionar filtros de conjunto de dados, filtros de região e filtros de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Referências de coleções de parâmetros &#40;Construtor de Relatórios e SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
