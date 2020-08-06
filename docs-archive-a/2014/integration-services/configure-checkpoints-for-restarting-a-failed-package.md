---
title: Configurar pontos de verificação para reiniciar um pacote com falha | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- checkpoints [Integration Services]
- restarting packages
- starting packages
ms.assetid: 9afffa5a-d803-4653-8afc-386453fc163f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a85354377453e0b24692ab8c2b567cc8998b6b05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683641"
---
# <a name="configure-checkpoints-for-restarting-a-failed-package"></a>Configurar pontos de verificação para reinicializar um pacote com falha
  Você pode configurar os pacotes [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para reiniciá-los a partir de um ponto de falha em vez de executar novamente todo o pacote, selecionando as propriedades que se aplicam aos pontos de verificação.  
  
### <a name="to-configure-a-package-to-restart"></a>Para configurar um pacote para reinicialização  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote que você deseja configurar.  
  
2.  No **Gerenciador de Soluções**, clique duas vezes no pacote para abri-lo.  
  
3.  Clique na guia **Fluxo de Controle** .  
  
4.  Clique com o botão direito do mouse em qualquer lugar da tela de fundo da superfície de design do fluxo de controle e clique em **Propriedades**.  
  
5.  Defina a Propriedade SaveCheckpoints como `True` .  
  
6.  Digite o nome do arquivo de ponto de verificação na propriedade CheckpointFileName.  
  
7.  Defina a propriedade CheckpointUsage como um dos dois valores:  
  
    -   Selecione `Always` para reiniciar o pacote partindo sempre de um ponto de verificação.  
  
        > [!IMPORTANT]  
        >  Um erro ocorrerá se o arquivo do ponto de verificação não estiver disponível.  
  
    -   Selecione `IfExists` para reiniciar o pacote apenas se o arquivo de ponto de verificação estiver disponível.  
  
8.  Configure as tarefas e os contêineres a partir dos quais o pacote pode ser reiniciado.  
  
    -   Clique com o botão direito do mouse em uma tarefa ou contêiner e clique em **Propriedades**.  
  
    -   Defina a Propriedade FailPackageOnFailure como `True` para cada tarefa e contêiner selecionados.  
  
## <a name="see-also"></a>Consulte Também  
 [Reiniciar pacotes por meio de pontos de verificação](packages/restart-packages-by-using-checkpoints.md)  
  
  
