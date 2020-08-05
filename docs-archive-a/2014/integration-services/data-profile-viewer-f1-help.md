---
title: Ajuda F1 do Visualizador de Perfil de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dataprofileviewer.f1
helpviewer_keywords:
- Data Profile Viewer [Integration Services]
- Data Profiling task [Integration Services], viewer
ms.assetid: 3469c60a-8f4f-46ba-999a-cb9070197fea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7003e1299938bd53a6d16a5597d4566ba5c46579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570779"
---
# <a name="data-profile-viewer-f1-help"></a><span data-ttu-id="e1b5b-102">Ajuda de F1 do Visualizador de Perfil de Dados</span><span class="sxs-lookup"><span data-stu-id="e1b5b-102">Data Profile Viewer F1 Help</span></span>
  <span data-ttu-id="e1b5b-103">Use o Visualizador de Perfil de Dados para exibir a saída da tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-103">Use the Data Profile Viewer to view the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="e1b5b-104">Para obter mais informações sobre como usar o Visualizador de Perfil de Dados, consulte [Visualizador de Perfil de Dados](control-flow/data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="e1b5b-104">For more information about how to use the Data Profile Viewer, see [Data Profile Viewer](control-flow/data-profile-viewer.md).</span></span> <span data-ttu-id="e1b5b-105">Para obter mais informações sobre como usar a tarefa Criação de Perfil de Dados, que cria a saída para análise no Visualizador de Perfil de Dados, consulte [Configuração da tarefa Criação de Perfil de Dados](control-flow/data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="e1b5b-105">For more information about how to use the Data Profiling task, which creates the profile output that you analyze in the Data Profile Viewer, see [Setup of the Data Profiling Task](control-flow/data-profiling-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="e1b5b-106">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="e1b5b-106">Static Options</span></span>  
 <span data-ttu-id="e1b5b-107">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-107">**Open**</span></span>  
 <span data-ttu-id="e1b5b-108">Clique para buscar o arquivo salvo que contém a saída da tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-108">Click to browse for the saved file that contains the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="e1b5b-109">Painel**Perfis**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-109">**Profiles** pane</span></span>  
 <span data-ttu-id="e1b5b-110">Expanda a árvore no painel **Perfis** para ver os perfis incluídos na saída.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-110">Expand the tree in the **Profiles** pane to see the profiles that are included in the output.</span></span> <span data-ttu-id="e1b5b-111">Selecione um perfil para exibir os seus resultados.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-111">Select a profile to view the results for that profile.</span></span>  
  
 <span data-ttu-id="e1b5b-112">Painel**Mensagens**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-112">**Message** pane</span></span>  
 <span data-ttu-id="e1b5b-113">Exibe mensagens de estado.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-113">Displays status messages.</span></span>  
  
 <span data-ttu-id="e1b5b-114">Painel**Busca Detalhada**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-114">**Drilldown** pane</span></span>  
 <span data-ttu-id="e1b5b-115">Exibe as linhas de dados que correspondem a um valor na saída, se a fonte de dados usada pela tarefa Criação de Perfil de dados estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-115">Displays the rows of data that match a value in the output, if the data source that is used by the Data Profiling task is available.</span></span>  
  
 <span data-ttu-id="e1b5b-116">Por exemplo, se estiver exibindo a saída de um perfil Distribuição de Valor de Coluna para uma coluna Estado dos Estados Unidos da América, o painel **Distribuição de Valor Detalhado** pode conter uma linha para "WA".</span><span class="sxs-lookup"><span data-stu-id="e1b5b-116">For example, if you are viewing the output of a Column Value Distribution profile for a US State column, the **Detailed Value Distribution** pane might contain a row for "WA".</span></span> <span data-ttu-id="e1b5b-117">Clique duas vezes na linha do painel **Distribuição de Valor Detalhado** para ver as linhas de dados nas quais o valor da coluna de estado é “WA” no painel de busca detalhada.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-117">Double-click the row in the **Detailed Value Distribution** pane to see the rows of data where the value of the state column is "WA" in the drilldown pane.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="e1b5b-118">Opções dinâmicas</span><span class="sxs-lookup"><span data-stu-id="e1b5b-118">Dynamic Options</span></span>  
  
### <a name="profile-type--column-length-distribution-profile"></a><span data-ttu-id="e1b5b-119">Tipo de Perfil = Perfil de Distribuição de Comprimento de Coluna</span><span class="sxs-lookup"><span data-stu-id="e1b5b-119">Profile Type = Column Length Distribution Profile</span></span>  
  
#### <a name="column-length-distribution-profile---column-pane"></a><span data-ttu-id="e1b5b-120">Perfil de Distribuição de Comprimento de Coluna – painel \<column></span><span class="sxs-lookup"><span data-stu-id="e1b5b-120">Column Length Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="e1b5b-121">**Comprimento Mínimo**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-121">**Minimum Length**</span></span>  
 <span data-ttu-id="e1b5b-122">Exibe o comprimento mínimo de valores nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-122">Displays the minimum length of values in this column.</span></span>  
  
 <span data-ttu-id="e1b5b-123">**Comprimento Máximo**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-123">**Maximum Length**</span></span>  
 <span data-ttu-id="e1b5b-124">Exibe o comprimento máximo de valores nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-124">Displays the maximum length of values in this column.</span></span>  
  
 <span data-ttu-id="e1b5b-125">**Ignorar Espaços à Esquerda**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-125">**Ignore Leading Spaces**</span></span>  
 <span data-ttu-id="e1b5b-126">Exibe se este perfil foi computado com um valor `IgnoreLeadingSpaces` de True ou False.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-126">Displays whether this profile was computed with an `IgnoreLeadingSpaces` value of True or False.</span></span> <span data-ttu-id="e1b5b-127">Esta propriedade foi definida na página **Solicitações de Perfil** do Editor de Tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-127">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="e1b5b-128">**Ignorar Espaços à Direita**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-128">**Ignore Trailing Spaces**</span></span>  
 <span data-ttu-id="e1b5b-129">Exibe se este perfil foi computado com um valor `IgnoreTrailingSpaces` de True ou False.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-129">Displays whether this profile was computed with an `IgnoreTrailingSpaces` value of True or False.</span></span> <span data-ttu-id="e1b5b-130">Esta propriedade foi definida na página **Solicitações de Perfil** do Editor de Tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-130">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="e1b5b-131">**Contagem de Linhas**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-131">**Row Count**</span></span>  
 <span data-ttu-id="e1b5b-132">Exibe o número de linhas na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-132">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-length-distribution-pane"></a><span data-ttu-id="e1b5b-133">Painel Distribuição de Comprimento Detalhado</span><span class="sxs-lookup"><span data-stu-id="e1b5b-133">Detailed Length Distribution pane</span></span>  
 <span data-ttu-id="e1b5b-134">**Comprimento**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-134">**Length**</span></span>  
 <span data-ttu-id="e1b5b-135">Exibe os comprimentos de coluna localizados na coluna perfilada.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-135">Displays the column lengths found in the profiled column.</span></span>  
  
 <span data-ttu-id="e1b5b-136">**Count**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-136">**Count**</span></span>  
 <span data-ttu-id="e1b5b-137">Exibe o número de linhas nas quais o valor da coluna cujo perfil está sendo criado tem o tamanho mostrado na coluna **Tamanho** .</span><span class="sxs-lookup"><span data-stu-id="e1b5b-137">Displays the number of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
 <span data-ttu-id="e1b5b-138">**Percentual**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-138">**Percentage**</span></span>  
 <span data-ttu-id="e1b5b-139">Exibe o percentual de linhas nas quais o valor da coluna cujo perfil está sendo criado tem o tamanho exibido na coluna **Tamanho** .</span><span class="sxs-lookup"><span data-stu-id="e1b5b-139">Displays the percentage of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
### <a name="profile-type--column-null-ratio-profile"></a><span data-ttu-id="e1b5b-140">Tipo de Perfil = Perfil de Razão Nula de Coluna</span><span class="sxs-lookup"><span data-stu-id="e1b5b-140">Profile Type = Column Null Ratio Profile</span></span>  
  
#### <a name="column-null-ratio-profile---column-pane"></a><span data-ttu-id="e1b5b-141">Perfil Razão Nula de Coluna – painel \<column></span><span class="sxs-lookup"><span data-stu-id="e1b5b-141">Column Null Ratio Profile - \<column> pane</span></span>  
 <span data-ttu-id="e1b5b-142">**Contagem Nula**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-142">**Null Count**</span></span>  
 <span data-ttu-id="e1b5b-143">Exibe o número de linhas nas quais a coluna perfilada tem um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-143">Displays the number of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="e1b5b-144">**Porcentagem Nula**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-144">**Null Percentage**</span></span>  
 <span data-ttu-id="e1b5b-145">Exibe a porcentagem de linhas nas quais a coluna cujo perfil está sendo criado tem um valor nulo</span><span class="sxs-lookup"><span data-stu-id="e1b5b-145">Displays the percentage of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="e1b5b-146">**Contagem de Linhas**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-146">**Row Count**</span></span>  
 <span data-ttu-id="e1b5b-147">Exibe o número de linhas na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-147">Displays the number of rows in the table or view.</span></span>  
  
### <a name="profile-type--column-pattern-profile"></a><span data-ttu-id="e1b5b-148">Tipo de Perfil = Perfil Padrão de Coluna</span><span class="sxs-lookup"><span data-stu-id="e1b5b-148">Profile Type = Column Pattern Profile</span></span>  
  
#### <a name="column-pattern-profile---column-pane"></a><span data-ttu-id="e1b5b-149">Perfil de Padrão de Coluna – painel \<column></span><span class="sxs-lookup"><span data-stu-id="e1b5b-149">Column Pattern Profile - \<column> pane</span></span>  
 <span data-ttu-id="e1b5b-150">**Contagem de Linhas**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-150">**Row Count**</span></span>  
 <span data-ttu-id="e1b5b-151">Exibe o número de linhas na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-151">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="pattern-distribution-pane"></a><span data-ttu-id="e1b5b-152">Painel Distribuição de Padrão</span><span class="sxs-lookup"><span data-stu-id="e1b5b-152">Pattern Distribution pane</span></span>  
 <span data-ttu-id="e1b5b-153">**Padrão**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-153">**Pattern**</span></span>  
 <span data-ttu-id="e1b5b-154">Exibe os padrões computados para a coluna cujo perfil está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-154">Displays the patterns computed for the profiled column.</span></span>  
  
 <span data-ttu-id="e1b5b-155">**Percentual**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-155">**Percentage**</span></span>  
 <span data-ttu-id="e1b5b-156">Exibe o percentual de linhas cujos valores correspondem ao padrão exibido na coluna **Padrão** .</span><span class="sxs-lookup"><span data-stu-id="e1b5b-156">Displays the percentage of rows whose values match the pattern displayed in the **Pattern** column.</span></span>  
  
### <a name="profile-type--column-statistics-profile"></a><span data-ttu-id="e1b5b-157">Tipo de Perfil = Perfil de Estatísticas da Coluna</span><span class="sxs-lookup"><span data-stu-id="e1b5b-157">Profile Type = Column Statistics Profile</span></span>  
  
#### <a name="column-statistics-profile---column-pane"></a><span data-ttu-id="e1b5b-158">Perfil Estatísticas de Coluna – painel \<column></span><span class="sxs-lookup"><span data-stu-id="e1b5b-158">Column Statistics Profile - \<column> pane</span></span>  
 <span data-ttu-id="e1b5b-159">**Mínimo**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-159">**Minimum**</span></span>  
 <span data-ttu-id="e1b5b-160">Exibe o valor mínimo localizado na coluna cujo perfil está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-160">Displays the minimum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="e1b5b-161">**Máximo**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-161">**Maximum**</span></span>  
 <span data-ttu-id="e1b5b-162">Exibe o valor máximo localizado na coluna cujo perfil está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-162">Displays the maximum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="e1b5b-163">**Mean**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-163">**Mean**</span></span>  
 <span data-ttu-id="e1b5b-164">Exibe a média dos valores encontrados na coluna cujo perfil está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-164">Displays the mean of the values found in the profiled column.</span></span>  
  
 <span data-ttu-id="e1b5b-165">**Desvio Padrão**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-165">**Standard Deviation**</span></span>  
 <span data-ttu-id="e1b5b-166">Exibe o desvio padrão dos valores encontrados na coluna cujo perfil está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-166">Displays the standard deviation of the values found in the profiled column.</span></span>  
  
### <a name="profile-type--column-value-distribution-profile"></a><span data-ttu-id="e1b5b-167">Tipo de Perfil = Perfil de Distribuição de Valor da Coluna</span><span class="sxs-lookup"><span data-stu-id="e1b5b-167">Profile Type = Column Value Distribution Profile</span></span>  
  
#### <a name="column-value-distribution-profile---column-pane"></a><span data-ttu-id="e1b5b-168">Perfil Distribuição de Valor de Coluna – painel \<column></span><span class="sxs-lookup"><span data-stu-id="e1b5b-168">Column Value Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="e1b5b-169">**Número de Valores Distintos**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-169">**Number of Distinct Values**</span></span>  
 <span data-ttu-id="e1b5b-170">Exibe a contagem de valores distintos encontrados na coluna cujo perfil está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-170">Displays the count of distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="e1b5b-171">**Contagem de Linhas**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-171">**Row Count**</span></span>  
 <span data-ttu-id="e1b5b-172">Exibe o número de linhas na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-172">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-value-distribution-pane"></a><span data-ttu-id="e1b5b-173">Painel Distribuição de Valor Detalhado</span><span class="sxs-lookup"><span data-stu-id="e1b5b-173">Detailed Value Distribution pane</span></span>  
 <span data-ttu-id="e1b5b-174">**Valor**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-174">**Value**</span></span>  
 <span data-ttu-id="e1b5b-175">Exibe os valores distintos encontrados na coluna cujo perfil está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-175">Displays the distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="e1b5b-176">**Count**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-176">**Count**</span></span>  
 <span data-ttu-id="e1b5b-177">Exibe o número de linhas nas quais a coluna cujo perfil está sendo criado tem o valor exibido na coluna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="e1b5b-177">Displays the number of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
 <span data-ttu-id="e1b5b-178">**Percentual**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-178">**Percentage**</span></span>  
 <span data-ttu-id="e1b5b-179">Exibe o percentual de linhas nas quais a coluna cujo perfil está sendo criado tem o valor exibido na coluna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="e1b5b-179">Displays the percentage of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
### <a name="profile-type--candidate-key-profile"></a><span data-ttu-id="e1b5b-180">Tipo de Perfil = Perfil-Chave de Candidato</span><span class="sxs-lookup"><span data-stu-id="e1b5b-180">Profile Type = Candidate Key Profile</span></span>  
  
#### <a name="candidate-key-profile---table-pane"></a><span data-ttu-id="e1b5b-181">Perfil Chave Candidata – painel \<table></span><span class="sxs-lookup"><span data-stu-id="e1b5b-181">Candidate Key Profile - \<table> pane</span></span>  
 <span data-ttu-id="e1b5b-182">**Colunas de Chave**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-182">**Key Columns**</span></span>  
 <span data-ttu-id="e1b5b-183">Exibe as colunas que foram selecionadas para criação de perfil como chave candidata.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-183">Displays the columns that were selected for profiling as a candidate key.</span></span>  
  
 <span data-ttu-id="e1b5b-184">**Intensidade de Chave**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-184">**Key Strength**</span></span>  
 <span data-ttu-id="e1b5b-185">Exibe a intensidade (em porcentagem) da coluna da chave candidata ou da combinação de colunas.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-185">Displays the strength (as a percentage) of the candidate key column or combination of columns.</span></span> <span data-ttu-id="e1b5b-186">Uma intensidade de chave inferior a 100% indica que existem valores em duplicata.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-186">A key strength of less than 100% indicates that duplicate values exist.</span></span>  
  
#### <a name="key-violations-pane"></a><span data-ttu-id="e1b5b-187">Painel Violações de Chave</span><span class="sxs-lookup"><span data-stu-id="e1b5b-187">Key Violations pane</span></span>  
 <span data-ttu-id="e1b5b-188">**\<column1>, \<column2> etc.**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-188">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="e1b5b-189">Exibe os valores em duplicata encontrados na coluna cujo perfil está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-189">Displays the duplicate values that were found in the profiled column.</span></span>  
  
 <span data-ttu-id="e1b5b-190">**Count**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-190">**Count**</span></span>  
 <span data-ttu-id="e1b5b-191">Exibe o número de linhas nas quais a coluna especificada tem o valor exibido na primeira coluna.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-191">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
### <a name="profile-type--functional-dependency-profile"></a><span data-ttu-id="e1b5b-192">Tipo de Perfil = Perfil de Dependência Funcional</span><span class="sxs-lookup"><span data-stu-id="e1b5b-192">Profile Type = Functional Dependency Profile</span></span>  
  
#### <a name="functional-dependency-profile-pane"></a><span data-ttu-id="e1b5b-193">Painel do perfil de Dependência Funcional</span><span class="sxs-lookup"><span data-stu-id="e1b5b-193">Functional Dependency Profile pane</span></span>  
 <span data-ttu-id="e1b5b-194">**Colunas Determinantes**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-194">**Determinant Columns**</span></span>  
 <span data-ttu-id="e1b5b-195">Exibe a coluna ou colunas selecionadas como coluna ou colunas determinantes.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-195">Displays the column or columns selected as the determinant column.</span></span> <span data-ttu-id="e1b5b-196">No exemplo no qual o mesmo Código Postal dos Estados Unidos deveria ter sempre o mesmo estado, a coluna Código Postal é a coluna determinante.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-196">In the example where the same United States Zip Code should always have the same state, the Zip Code is the determinant column.</span></span>  
  
 <span data-ttu-id="e1b5b-197">**Colunas Dependentes**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-197">**Dependent Columns**</span></span>  
 <span data-ttu-id="e1b5b-198">Exibe a coluna ou colunas selecionadas como coluna ou colunas dependentes.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-198">Displays the column or columns selected as the dependent column.</span></span> <span data-ttu-id="e1b5b-199">No exemplo no qual o mesmo Código Postal dos Estados Unidos deveria ter sempre o mesmo estado, a coluna Estado é a coluna dependente.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-199">In the example where the same United States Zip Code should always have the same state, the state is the dependent column.</span></span>  
  
 <span data-ttu-id="e1b5b-200">**Intensidade de Dependência Funcional**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-200">**Functional Dependency Strength**</span></span>  
 <span data-ttu-id="e1b5b-201">Exibe a intensidade (em porcentagem) da dependência funcional entre colunas.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-201">Displays the strength (as a percentage) of the functional dependency between columns.</span></span> <span data-ttu-id="e1b5b-202">Uma intensidade de chave inferior a 100% indica que há casos nos quais o valor determinante não determina o valor dependente.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-202">A key strength of less than 100% indicates that there are cases where the determinant value does not determine the dependent value.</span></span> <span data-ttu-id="e1b5b-203">No exemplo no qual o mesmo Código Postal dos Estados Unidos deveria ter sempre o mesmo estado, isso provavelmente indica que alguns valores de estado são inválidos</span><span class="sxs-lookup"><span data-stu-id="e1b5b-203">In the example where the same United States Zip Code should always have the same state, this probably indicates some state values are not valid.</span></span>  
  
#### <a name="functional-dependency-violations-pane"></a><span data-ttu-id="e1b5b-204">Painel Violações de Dependência Funcional</span><span class="sxs-lookup"><span data-stu-id="e1b5b-204">Functional Dependency Violations pane</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1b5b-205">Uma porcentagem alta de valores errôneos nos dados poderia conduzir a resultados inesperados de um perfil Dependência Funcional.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-205">A high percentage of erroneous values in the data could lead to unexpected results from a Functional Dependency profile.</span></span> <span data-ttu-id="e1b5b-206">Por exemplo, 90% das linhas têm um valor de “WI” em Estado para um valor de Código Postal de "98052".</span><span class="sxs-lookup"><span data-stu-id="e1b5b-206">For example, 90% of the rows have a State value of "WI" for a Postal Code value of "98052."</span></span> <span data-ttu-id="e1b5b-207">O perfil informa linhas que contêm o valor de estado correto de "WA" como violações.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-207">The profile reports rows that contain the correct state value of "WA" as violations.</span></span>  
  
 **\<determinant column name>**  
 <span data-ttu-id="e1b5b-208">Exibe o valor da coluna determinante ou combinação de colunas na instância de uma violação de dependência funcional.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-208">Displays the value of the determinant column or combination of columns in this instance of a functional dependency violation.</span></span>  
  
 **\<dependent column name>**  
 <span data-ttu-id="e1b5b-209">Exibe o valor da coluna dependente na instância de uma violação de dependência funcional.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-209">Displays the value of the dependent column in this instance of a functional dependency violation.</span></span>  
  
 <span data-ttu-id="e1b5b-210">**Contagem de Suporte**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-210">**Support Count**</span></span>  
 <span data-ttu-id="e1b5b-211">Exibe o número de linhas nas quais o valor de coluna determinante determina a coluna dependente.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-211">Displays the number of rows in which the determinant column value determines the dependent column.</span></span>  
  
 <span data-ttu-id="e1b5b-212">**Contagem de Violação**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-212">**Violation Count**</span></span>  
 <span data-ttu-id="e1b5b-213">Exibe o número de linhas nas quais o valor de coluna determinante não determina a coluna dependente</span><span class="sxs-lookup"><span data-stu-id="e1b5b-213">Displays the number of rows in which the determinant column value does not determine the dependent column.</span></span> <span data-ttu-id="e1b5b-214">(Linhas em que o valor dependente é o valor exibido na coluna **\<dependent column name>** .)</span><span class="sxs-lookup"><span data-stu-id="e1b5b-214">(These are the rows where the dependent value is the value shown in the **\<dependent column name>** column.)</span></span>  
  
 <span data-ttu-id="e1b5b-215">**Percentual de Suporte**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-215">**Support Percentage**</span></span>  
 <span data-ttu-id="e1b5b-216">Exibe a porcentagem de linhas nas quais a coluna determinante determina a coluna dependente.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-216">Displays the percentage of rows in which the determinant column determines the dependent column.</span></span>  
  
### <a name="profile-type--value-inclusion-profile"></a><span data-ttu-id="e1b5b-217">Tipo de Perfil = Perfil de Inclusão de Valor</span><span class="sxs-lookup"><span data-stu-id="e1b5b-217">Profile Type = Value Inclusion Profile</span></span>  
  
#### <a name="value-inclusion-profile-pane"></a><span data-ttu-id="e1b5b-218">Painel do Perfil de Inclusão de Valor</span><span class="sxs-lookup"><span data-stu-id="e1b5b-218">Value Inclusion Profile pane</span></span>  
 <span data-ttu-id="e1b5b-219">**Colunas Laterais de Subconjunto**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-219">**Subset Side Columns**</span></span>  
 <span data-ttu-id="e1b5b-220">Exibe a coluna ou combinação de colunas cujo perfil foi criado para determinar se elas estão nas colunas do superconjunto.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-220">Displays the column or combination of columns that were profiled to determine whether they are in the superset columns.</span></span>  
  
 <span data-ttu-id="e1b5b-221">**Colunas Laterais de Superconjunto**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-221">**Superset Side Columns**</span></span>  
 <span data-ttu-id="e1b5b-222">Exibe a coluna ou combinação de colunas cujo perfil foi criado para determinar se elas incluem os valores nas colunas do subconjunto.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-222">Displays the column or combination of columns that were profiled to determine whether they include the values in the subset columns.</span></span>  
  
 <span data-ttu-id="e1b5b-223">**Intensidade de Inclusão**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-223">**Inclusion Strength**</span></span>  
 <span data-ttu-id="e1b5b-224">Exibe a intensidade (em porcentagem) da sobreposição entre colunas.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-224">Displays the strength (as a percentage) of the overlap between columns.</span></span> <span data-ttu-id="e1b5b-225">Uma intensidade de chave inferior a 100% indica que há casos nos quais o valor do subconjunto não está localizado entre os valores do superconjunto.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-225">A key strength of less than 100% indicates that there are cases where the subset value is not found among the superset values.</span></span>  
  
#### <a name="inclusion-violations-pane"></a><span data-ttu-id="e1b5b-226">Painel Violações de Inclusão</span><span class="sxs-lookup"><span data-stu-id="e1b5b-226">Inclusion Violations pane</span></span>  
 <span data-ttu-id="e1b5b-227">**\<column1>, \<column2> etc.**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-227">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="e1b5b-228">Exibe os valores na coluna de subconjunto ou colunas que não foram localizadas na coluna ou colunas do superconjunto.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-228">Displays the values in the subset column or columns that were not found in the superset column or columns.</span></span>  
  
 <span data-ttu-id="e1b5b-229">**Count**</span><span class="sxs-lookup"><span data-stu-id="e1b5b-229">**Count**</span></span>  
 <span data-ttu-id="e1b5b-230">Exibe o número de linhas nas quais a coluna especificada tem o valor exibido na primeira coluna.</span><span class="sxs-lookup"><span data-stu-id="e1b5b-230">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1b5b-231">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e1b5b-231">See Also</span></span>  
 <span data-ttu-id="e1b5b-232">[Visualizador de Perfil de Dados](control-flow/data-profile-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="e1b5b-232">[Data Profile Viewer](control-flow/data-profile-viewer.md) </span></span>  
 [<span data-ttu-id="e1b5b-233">Tarefa e visualizador da tarefa Criação de Perfil de Dados</span><span class="sxs-lookup"><span data-stu-id="e1b5b-233">Data Profiling Task and Viewer</span></span>](control-flow/data-profiling-task-and-viewer.md)  
  
  
