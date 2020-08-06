---
title: Editor de fonte de arquivo simples (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.columns.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: b5af5f65-c087-44fd-b5ae-d0441245fef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9b0249b2b17d50fdef4b5cf4aff70a1318614257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570151"
---
# <a name="flat-file-source-editor-columns-page"></a>Editor de Fonte de Arquivo Simples (página Colunas)
  Use o nó **Colunas** da caixa de diálogo **Editor de Fonte de Arquivo Simples** para mapear uma coluna de saída para cada coluna externa (fonte).  
  
> [!NOTE]  
>  A `FileNameColumnName` propriedade da fonte de arquivo simples e a `FastParse` propriedade de suas colunas de saída não estão disponíveis no **Editor de fonte de arquivo simples**, mas podem ser definidas usando o **Editor avançado**. Para obter mais informações sobre estas propriedades, consulte a seção Fonte de Arquivo Simples em [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).  
  
 Para saber mais sobre a fonte de Arquivo Simples, consulte [Flat File Source](data-flow/flat-file-source.md).  
  
## <a name="options"></a>Opções  
 **Colunas Externas Disponíveis**  
 Exiba a lista de colunas externas disponíveis na fonte de dados. Você não pode usar esta tabela para adicionar ou excluir colunas.  
  
 **Coluna Externa**  
 Exiba as colunas externas (fonte) na ordem em que serão lidas pela tarefa. É possível alterar esta ordem desmarcando as colunas selecionadas na tabela e selecionando as colunas externas da lista em uma ordem diferente.  
  
 **Coluna de Saída**  
 Forneça um nome exclusivo para cada coluna de saída. O padrão é o nome da coluna externa (origem) selecionada; porém, é possível escolher qualquer nome descritivo exclusivo. O nome fornecido será exibido no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor de fonte de arquivo simples &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md)   
 [Editor de fonte de arquivo simples &#40;página saída de erro&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md)   
 [Gerenciador de Conexões de Arquivos Simples](connection-manager/file-connection-manager.md)  
  
  
