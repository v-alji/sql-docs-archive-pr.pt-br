---
title: 'Tarefa 3: limpando dados em relação à base de conhecimento dos fornecedores | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 647c924a-9b91-4294-8d96-e81416e4e90e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 13201a8b904a5fc5232b9fa860710e4e39cce67a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683174"
---
# <a name="task-3-cleansing-data-against-the-suppliers-knowledge-base"></a><span data-ttu-id="ceef4-102">Tarefa 3: Limpando dados em relação à base de dados de conhecimento de fornecedores</span><span class="sxs-lookup"><span data-stu-id="ceef4-102">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="ceef4-103">Nesta tarefa, você executará o processo de limpeza auxiliado por computador.</span><span class="sxs-lookup"><span data-stu-id="ceef4-103">In this task, you run the computer-assisted cleansing process.</span></span> <span data-ttu-id="ceef4-104">O DQS usa algoritmos avançados e níveis de confiança baseados nos valores de limite especificados para analisar os dados em relação à base de dados de conhecimento selecionada e depois limpá-los.</span><span class="sxs-lookup"><span data-stu-id="ceef4-104">DQS uses advanced algorithms and confidence levels based on the threshold values specified to analyze the data against the selected knowledge base, and then cleanse it.</span></span> <span data-ttu-id="ceef4-105">Consulte [limpeza de dados usando o conhecimento do DQS (interno)](https://msdn.microsoft.com/library/hh213061.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="ceef4-105">See [Cleansing Data Using DQS (Internal) Knowledge](https://msdn.microsoft.com/library/hh213061.aspx) for more details.</span></span>

1.  <span data-ttu-id="ceef4-106">Clique em **Iniciar** para iniciar o processo de limpeza auxiliada por computador.</span><span class="sxs-lookup"><span data-stu-id="ceef4-106">Click **Start** to start the computer-assisted cleansing process.</span></span>

     <span data-ttu-id="ceef4-107">![Página Limpar do processo de limpeza](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-01.jpg "Página Limpar do processo de limpeza")</span><span class="sxs-lookup"><span data-stu-id="ceef4-107">![Cleanse Page of the Cleansing Process](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-01.jpg "Cleanse Page of the Cleansing Process")</span></span>

2.  <span data-ttu-id="ceef4-108">Quando o processo de limpeza for concluído, examine **estatísticas** na guia **criador de perfil** . As estatísticas de origem fornecem o número de registros processados, o número de registros que são considerados corretos, o número de registros que o DQS corrige, o número de registros que têm alterações sugeridas pelo DQS e o número de registros que são inválidos.</span><span class="sxs-lookup"><span data-stu-id="ceef4-108">When the cleansing process is completed, review **statistics** in the **Profiler** tab. The Source Statistics provide the number of records processed, number of records that are found to be correct, number of records that DQS corrects, number of records that have changes suggested by DQS, and the number of records that are invalid.</span></span> <span data-ttu-id="ceef4-109">Na caixa de listagem à direita, você pode visualizar os valores corrigidos, os valores sugeridos e a integridade (até que ponto os dados estão presentes) e a precisão (até que ponto os dados podem ser usados para os fins pretendidos) de valores para cada domínio envolvido no processo de limpeza.</span><span class="sxs-lookup"><span data-stu-id="ceef4-109">In the list box to the right, you can see the corrected values, suggested values, and the completeness (the extent to which the data is present) and accuracy (the extent to which the data can be used for intended purposes) of values for each domain involved in the cleansing process.</span></span>

     <span data-ttu-id="ceef4-110">![Resultados da limpeza](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-02.jpg "Resultados da limpeza")</span><span class="sxs-lookup"><span data-stu-id="ceef4-110">![Cleansing Results](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-02.jpg "Cleansing Results")</span></span>

3.  <span data-ttu-id="ceef4-111">Clique em **Avançar** para alternar para a página **gerenciar e exibir resultados** .</span><span class="sxs-lookup"><span data-stu-id="ceef4-111">Click **Next** to switch to **Manage and View Results** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="ceef4-112">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ceef4-112">Next Step</span></span>
 [<span data-ttu-id="ceef4-113">Tarefa 4: Gerenciando e exibindo resultados</span><span class="sxs-lookup"><span data-stu-id="ceef4-113">Task 4: Manaing and Viewing Results</span></span>](../../2014/tutorials/task-4-manaing-and-viewing-results.md)


