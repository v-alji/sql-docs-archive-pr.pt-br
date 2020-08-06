---
title: 'Lição 2: limpando dados de fornecedores usando a base de dados de conhecimento dos fornecedores | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 215c14de-fc3f-46de-a022-bf69b9ea2a96
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ebc0231cd0f28fcad23656cf22abd8d68eca7dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568966"
---
# <a name="lesson-2-cleansing-supplier-data-using-the-suppliers-knowledge-base"></a><span data-ttu-id="d3766-102">Lição 2: Limpando dados de fornecedor usando a base de dados de conhecimento de fornecedores</span><span class="sxs-lookup"><span data-stu-id="d3766-102">Lesson 2: Cleansing Supplier Data using the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="d3766-103">Nesta lição, você limpará os dados de fornecedores em um arquivo do Excel usando a base de dados de conhecimento dos **fornecedores** que você criou na primeira lição.</span><span class="sxs-lookup"><span data-stu-id="d3766-103">In this lesson, you cleanse the supplier data in an Excel file by using the **Suppliers** knowledge base you have created in the first lesson.</span></span> <span data-ttu-id="d3766-104">A limpeza de dados no DQS inclui um **processo auxiliado por computador** que analisa como os dados estão em conformidade com o conhecimento em uma base de dados de conhecimento e um **processo interativo** que permite revisar e modificar os resultados do processo assistido por computador.</span><span class="sxs-lookup"><span data-stu-id="d3766-104">Data cleansing in DQS includes a **computer-assisted process** that analyzes how data conforms to the knowledge in a knowledge base, and an **interactive process** that enables you to review and modify results from the computer-assisted process.</span></span> <span data-ttu-id="d3766-105">O recurso de limpeza de dados identifica dados incorretos na fonte de dados e corrige ou sugere correções para os dados incorretos.</span><span class="sxs-lookup"><span data-stu-id="d3766-105">The data cleansing feature identifies incorrect data in your data source and then corrects or suggests corrections for the incorrect data.</span></span> <span data-ttu-id="d3766-106">Também padroniza e enriquece dados de cliente usando valores de domínio, valores principais para sinônimos, regras de domínio, relações baseadas em termos e dados de referência.</span><span class="sxs-lookup"><span data-stu-id="d3766-106">It also standardizes and enriches customer data by using domain values, leading values for synonyms, domain rules, term-based relations, and reference data.</span></span> <span data-ttu-id="d3766-107">Você pode aprovar ou rejeitar interativamente as alterações propostas pelo processo auxiliado por computador.</span><span class="sxs-lookup"><span data-stu-id="d3766-107">You can interactively approve or reject changes proposed by the computer-assisted process.</span></span> <span data-ttu-id="d3766-108">Consulte [limpeza de dados](https://msdn.microsoft.com/library/gg524800.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d3766-108">See [Data Cleansing](https://msdn.microsoft.com/library/gg524800.aspx) for more details.</span></span>  
  
 <span data-ttu-id="d3766-109">O processo auxiliado por computador usa os valores de limite a seguir que você pode configurar usando a opção Configuração na página principal do Cliente DQS.</span><span class="sxs-lookup"><span data-stu-id="d3766-109">The computer-assisted process uses the following threshold values that you can configure using the Configuration option on the DQS Client main page.</span></span>  
  
-   <span data-ttu-id="d3766-110">**Pontuação mínima para sugestões:** A pontuação mínima ou o nível de confiança usado pelo DQS para sugerir a substituição de um valor.</span><span class="sxs-lookup"><span data-stu-id="d3766-110">**Min score for suggestions:** The minimum score or confidence level that is used by DQS for suggesting replacement for a value.</span></span>  
  
-   <span data-ttu-id="d3766-111">**Pontuação mínima para correções automáticas:** A pontuação mínima ou o nível de confiança usado pelo DQS para corrigir automaticamente um valor.</span><span class="sxs-lookup"><span data-stu-id="d3766-111">**Min score for auto corrections:** The minimum score or confidence level that is used by DQS for automatically correcting a value.</span></span>  
  
 <span data-ttu-id="d3766-112">Consulte [Configurar valores de limite para limpeza e correspondência](https://msdn.microsoft.com/library/hh510415.aspx) para obter detalhes sobre como definir essas configurações.</span><span class="sxs-lookup"><span data-stu-id="d3766-112">See [Configure Threshold Values for Cleansing and Matching](https://msdn.microsoft.com/library/hh510415.aspx) for details on how to configure these settings.</span></span>  
  
 <span data-ttu-id="d3766-113">Nesta lição, você executará as seguintes tarefas para limpar os dados de entrada usando a base de dados de conhecimento Fornecedores.</span><span class="sxs-lookup"><span data-stu-id="d3766-113">In this lesson, you perform the following tasks to cleanse the input data by using the Suppliers knowledge base.</span></span>  
  
1.  <span data-ttu-id="d3766-114">Crie um Projeto do Data Quality para Limpeza, selecione a base de dados de conhecimento Fornecedores como a base de dados de conhecimento a ser usada para analisar e limpar os dados de origem em um arquivo do Excel e selecione a atividade Limpeza.</span><span class="sxs-lookup"><span data-stu-id="d3766-114">Create a Data Quality Project for Cleansing, select the Suppliers knowledge base as the knowledge base to use to analyze and cleanse the source data in an Excel file, and select the Cleansing activity.</span></span>  
  
2.  <span data-ttu-id="d3766-115">Mapeie as colunas do Excel que você deseja limpar para os domínios do DQS/domínios compostos apropriados na base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="d3766-115">Map the Excel columns that you want to cleanse to appropriate DQS domains/composite domains in the knowledge base.</span></span>  
  
3.  <span data-ttu-id="d3766-116">Execute a atividade de limpeza auxiliada por computador.</span><span class="sxs-lookup"><span data-stu-id="d3766-116">Run the computer-assisted cleansing activity.</span></span> <span data-ttu-id="d3766-117">O processo auxiliado por computador exibe informações de qualidade de dados no Cliente do Data Quality que você pode usar para limpar os dados interativamente.</span><span class="sxs-lookup"><span data-stu-id="d3766-117">The computer-assisted process displays data quality information in the Data Quality Client that you can use to cleanse the data interactively.</span></span>  
  
4.  <span data-ttu-id="d3766-118">Exiba e gerencie os resultados da atividade de limpeza.</span><span class="sxs-lookup"><span data-stu-id="d3766-118">View and manage the results of the cleansing activity.</span></span> <span data-ttu-id="d3766-119">Você pode examinar os valores que o processo auxiliado pelo computador considerar corretos, incorretos mas corrigidos, incorretos com uma alteração sugerida ou inválidos.</span><span class="sxs-lookup"><span data-stu-id="d3766-119">You can review the values that the computer-assisted process finds to be correct, incorrect but corrected, incorrect with a suggested change, or invalid.</span></span> <span data-ttu-id="d3766-120">Você pode aprovar ou rejeitar interativamente as alterações, corrigir ou substituir a sugestão do processo auxiliado pelo computador usando o campo Corrigir para.</span><span class="sxs-lookup"><span data-stu-id="d3766-120">You can interactively approve or reject changes, correcting or overriding the suggestion from the computer-assisted process by using the Correct To field.</span></span>  
  
5.  <span data-ttu-id="d3766-121">Exporte os resultados do processo de limpeza para um arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="d3766-121">Export the results from the cleansing process to an Excel file.</span></span>  
  
6.  <span data-ttu-id="d3766-122">Importe os valores do projeto de limpeza em domínios para aumentar o conhecimento na base de dados de conhecimento com novas regras, valores, correções etc...</span><span class="sxs-lookup"><span data-stu-id="d3766-122">Import the values from the cleansing project into domains to augment the knowledge in the knowledge base with new rules, values, corrections etc...</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d3766-123">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="d3766-123">Next Step</span></span>  
 [<span data-ttu-id="d3766-124">Tarefa 1: Criando um Projeto de Qualidade de Dados</span><span class="sxs-lookup"><span data-stu-id="d3766-124">Task 1: Creating a Data Quality Project</span></span>](../../2014/tutorials/task-1-creating-a-data-quality-project.md)  
  
  
