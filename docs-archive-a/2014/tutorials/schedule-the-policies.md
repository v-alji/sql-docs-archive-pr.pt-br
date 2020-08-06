---
title: Agendar as políticas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 59417a54-55f1-4468-ba41-368aa852c2d4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 1bce1b9d650606e9485899c34c72ca6b27a72dae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683186"
---
# <a name="schedule-the-policies"></a>Agendar as políticas
  Nesta tarefa, você agendará as políticas de práticas recomendadas que você importou na tarefa anterior.  
  
### <a name="to-schedule-the-best-practices-policies"></a>Para agendar as políticas de práticas recomendadas  
  
1.  No Pesquisador de objetos, expanda **Gerenciamento**, **Gerenciamento de políticas**, expanda **políticas**, clique com o botão direito do mouse em uma política de práticas recomendadas e clique em **Propriedades**.  
  
    > [!NOTE]  
    >  Como alternativa, para ver facilmente quais políticas estão associadas às práticas recomendadas e para classificar as categorias de práticas recomendadas, expanda **Gerenciamento**, expanda **Gerenciamento de políticas**e clique em **políticas**. No menu **Exibir** , clique em **Detalhes do Pesquisador de Objetos**. No painel **detalhes** do pesquisador de objetos, clique no título **categoria** para classificar as políticas por categoria. As políticas de práticas recomendadas têm o prefixo práticas **recomendadas da Microsoft**. Clique com o botão direito do mouse na política que você deseja configurar e clique em **Propriedades**.  
  
2.  Na página **geral** da caixa de diálogo **abrir política** , na lista **modo de avaliação** , clique **em agendar**.  
  
3.  Ao lado da caixa **agenda** , clique em **escolher** para especificar uma agenda existente ou clique em **novo** para criar uma nova agenda.  
  
4.  Depois de configurar uma agenda, você pode marcar a caixa de seleção **habilitado** na parte superior da página para habilitar a política agendada.  
  
5.  Repita as etapas de 1 a 4 para cada política que você deseja agendar.  
  
    > [!NOTE]  
    >  Para exibir os resultados da avaliação após a execução de uma diretiva agendada, abra o log Histórico da Diretiva na instância de destino. Para abrir o log, clique com o botão direito do mouse em **Gerenciamento de políticas**e clique em **Exibir histórico**.  
  
## <a name="summary"></a>Resumo  
 Você configurou políticas agendadas para serem executadas em uma única instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Se você desejar implantar políticas agendadas em várias instâncias, continue na próxima tarefa deste tutorial.  
  
## <a name="next-steps"></a>Próximas etapas  
 [Implantar diretivas agendadas em várias instâncias](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
  
