---
title: Especificando um conjunto de dados de teste para a estrutura (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75cd508f-b126-418b-848d-3c4c3e6c303f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c1430706a0ec2cd3ddc0eaee18d7001d05fefae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568958"
---
# <a name="specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial"></a>Especificando um conjunto de dados de teste para a estrutura (Tutorial de mineração de dados básico)
  Nas últimas telas do Assistente de Mineração de Dados, você dividirá seus dados entre um conjunto de teste e um conjunto de treinamento. Em seguida, dará um nome à sua estrutura e habilitará o detalhamento do modelo.  
  
## <a name="specifying-a-testing-set"></a>Especificando um conjunto de teste  
 A separação dos dados em conjuntos de treinamento e de teste na criação de uma estrutura de mineração possibilita a avaliação fácil da precisão dos modelos de mineração criados posteriormente. Para obter mais informações sobre conjuntos de testes, consulte [conjuntos de dados de treinamento e teste](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).  
  
#### <a name="to-specify-the-testing-set"></a>Para especificar o conjunto de teste  
  
1.  Na página **criar conjunto de testes** , para **percentual de dados para teste**, deixe o valor padrão de `30` .  
  
2.  Para o **número máximo de casos no conjunto de dados de teste**, digite `1000` .  
  
3.  Clique em **Avançar**.  
  
## <a name="specifying-drillthrough"></a>Especificando o detalhamento  
 O detalhamento pode ser habilitado em modelos e em estruturas. A caixa de seleção nesta caixa de diálogo permite o detalhamento no modelo nomeado. Depois que o modelo tiver sido processado, você poderá recuperar as informações detalhadas dos dados de treinamento que foram usados para criar o modelo.  
  
 Se a estrutura de mineração subjacente também estiver configurada para permitir o detalhamento, você poderá recuperar informações detalhadas dos casos de modelo e da estrutura de mineração, inclusive colunas que não foram incluídas no modelo de mineração. Para obter mais informações, consulte [Consultas de detalhamento &#40;Mineração de dados&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).  
  
#### <a name="to-name-the-model-and-structure-and-specify-drillthrough"></a>Para nomear o modelo e a estrutura e especificar o detalhamento  
  
1.  Na página **concluindo o assistente** , em **nome da estrutura de mineração**, digite `Targeted Mailing` .  
  
2.  Em **nome do modelo de mineração**, digite `TM_Decision_Tree` .  
  
3.  Marque a caixa de seleção **permitir Drill-through** .  
  
4.  Examine o painel de **Visualização** . Observe que somente as colunas selecionadas como **chave**, **entrada** ou **previsível** são mostradas. As outras colunas selecionadas (como AddressLine1, por exemplo) não são usadas para a criação do modelo, mas estarão disponíveis na estrutura subjacente e podem ser consultadas após o processamento e a implantação do modelo.  
  
5.  Clique em **Concluir**.  
  
## <a name="previous-task-in-lesson"></a>Tarefa anterior da lição  
 [Especificando o tipo de dados e o tipo de conteúdo &#40;tutorial de mineração de dados básico&#41;](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a>Próxima lição  
 [Lição 3: Adicionando e processando modelos](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Habilitar detalhamento para um modelo de mineração](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md)   
 [Consultas de detalhamento &#40;mineração de dados&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)   
 [Especifique os dados de treinamento &#40;assistente de mineração de dados&#41;](../../2014/analysis-services/specify-the-training-data-data-mining-wizard.md)  
  
  
