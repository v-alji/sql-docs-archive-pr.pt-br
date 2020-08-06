---
title: Criar um relatório de validação cruzada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- validating data mining models
- mining structures [Analysis Services], how-to topics
- cross-validation [data mining]
- statistical standard deviation
ms.assetid: 7b1fec4c-7053-41eb-b030-5179257967a4
author: minewiskan
ms.author: owend
ms.openlocfilehash: ccbafe63b0026cd45a15ea71fd84e223c1b32a9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678355"
---
# <a name="create-a-cross-validation-report"></a><span data-ttu-id="796e2-102">Criar um relatório de validação cruzada</span><span class="sxs-lookup"><span data-stu-id="796e2-102">Create a Cross-Validation Report</span></span>
  <span data-ttu-id="796e2-103">Este tópico mostra passo-a-passo a criação de um relatório de validação cruzada usando a guia Gráfico de Precisão no Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="796e2-103">This topic walks you through creation of a cross-validation report using the Accuracy Chart tab in Data Mining Designer.</span></span> <span data-ttu-id="796e2-104">Para obter informações gerais sobre a aparência de um relatório de validação cruzada e as medidas estatísticas que ele inclui, consulte [Validação cruzada &#40;Analysis Services – Mineração de Dados&#41;](cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="796e2-104">For general information about what a cross-validation report looks like, and the statistical measures it includes, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](cross-validation-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="796e2-105">Um relatório de validação cruzada é bem diferente de um gráfico de precisão, como um gráfico de comparação de precisão ou uma matriz de classificação.</span><span class="sxs-lookup"><span data-stu-id="796e2-105">A cross-validation report is fundamentally different from an accuracy chart, such as a lift chart or classification matrix.</span></span>  
  
-   <span data-ttu-id="796e2-106">A validação cruzada avalia a distribuição geral de dados que são usados em um modelo ou estrutura; assim, você não especifica um conjunto de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="796e2-106">Cross-validation assesses the overall distribution of data that is used in a model or structure; therefore, you do not specify a testing data set.</span></span> <span data-ttu-id="796e2-107">A validação cruzada sempre usa apenas os dados originais que foram usados para treinar o modelo ou a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="796e2-107">Cross-validation always uses only the original data that was used to train the model or the mining structure.</span></span>  
  
-   <span data-ttu-id="796e2-108">A validação cruzada só pode ser executada em relação a um único resultado previsível.</span><span class="sxs-lookup"><span data-stu-id="796e2-108">Cross-validation can only be performed with respect to a single predictable outcome.</span></span> <span data-ttu-id="796e2-109">Se a estrutura oferecer suporte a modelos com atributos previsíveis diferentes, crie relatórios separados para cada saída previsível.</span><span class="sxs-lookup"><span data-stu-id="796e2-109">If the structure supports models that have different predictable attributes, you must create separate reports for each predictable output.</span></span>  
  
-   <span data-ttu-id="796e2-110">Somente modelos relacionados à estrutura atual selecionada estão disponíveis para validação cruzada.</span><span class="sxs-lookup"><span data-stu-id="796e2-110">Only models that are related to the currently selected structure are available for cross-validation.</span></span>  
  
-   <span data-ttu-id="796e2-111">Se a estrutura selecionada no momento der suporte a uma combinação de modelos de clustering e não clustering, quando você clicar em **Obter Resultados**, o procedimento armazenado de validação cruzada carregará automaticamente modelos que têm a mesma coluna previsível, e ignorará modelos de clustering que não compartilham o mesmo atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="796e2-111">If the structure that is currently selected supports a combination of clustering and non-clustering models, when you click **Get Results**, the cross-validation stored procedure will automatically load models that have the same predicted column, and ignore clustering models that do not share the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="796e2-112">Você pode criar um relatório de validação cruzada em um modelo de clustering que não tem um atributo previsível somente quando a estrutura de mineração não oferece suporte a outros atributos previsíveis.</span><span class="sxs-lookup"><span data-stu-id="796e2-112">You can create a cross-validation report on a clustering model that does not have a predictable attribute only if the mining structure does not support any other predictable attributes.</span></span>  
  
### <a name="select-a-mining-structure"></a><span data-ttu-id="796e2-113">Selecionar uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="796e2-113">Select a mining structure</span></span>  
  
1.  <span data-ttu-id="796e2-114">Abra o Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="796e2-114">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="796e2-115">No Gerenciador de Soluções, abra o banco de dados que contém a estrutura ou o modelo para o qual você deseja criar um relatório.</span><span class="sxs-lookup"><span data-stu-id="796e2-115">In Solution Explorer, open the database that contains the structure or model for which you want to create a report.</span></span>  
  
3.  <span data-ttu-id="796e2-116">Clique duas vezes na estrutura de mineração para abrir a estrutura e seus modelos relacionados no Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="796e2-116">Double-click the mining structure to open the structure and its related models in Data Mining Designer.</span></span>  
  
4.  <span data-ttu-id="796e2-117">Clique na guia **Gráfico de Precisão de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="796e2-117">Click the **Mining Accuracy Chart** tab.</span></span>  
  
5.  <span data-ttu-id="796e2-118">Clique na guia **Validação Cruzada** .</span><span class="sxs-lookup"><span data-stu-id="796e2-118">Click the **Cross Validation** tab.</span></span>  
  
### <a name="set-cross-validation-options"></a><span data-ttu-id="796e2-119">Defina opções de validação cruzada</span><span class="sxs-lookup"><span data-stu-id="796e2-119">Set cross-validation options</span></span>  
  
1.  <span data-ttu-id="796e2-120">Na guia **Validação Cruzada** de **Número de Partições**, clique na seta para baixo para selecionar um número entre 1 e 10.</span><span class="sxs-lookup"><span data-stu-id="796e2-120">On the **Cross Validation** tab, for **Fold Count**, click the down arrow to select a number between 1 and 10.</span></span> <span data-ttu-id="796e2-121">O valor padrão é 10.</span><span class="sxs-lookup"><span data-stu-id="796e2-121">The default value is 10.</span></span>  
  
     <span data-ttu-id="796e2-122">O **Número de Partições** representa o número de partições que serão criadas dentro do conjunto de dados original.</span><span class="sxs-lookup"><span data-stu-id="796e2-122">The **Fold Count** represents the number of partitions that will be created within the original data set.</span></span> <span data-ttu-id="796e2-123">Se você definir Número de Partições como 1, será usado o conjunto de treinamento sem particionamento.</span><span class="sxs-lookup"><span data-stu-id="796e2-123">If you set Fold Count to 1, the training set will be used without partitioning.</span></span>  
  
2.  <span data-ttu-id="796e2-124">Em **Atributo de Destino**, clique na seta para baixo e selecione uma coluna na lista.</span><span class="sxs-lookup"><span data-stu-id="796e2-124">For **Target Attribute**, click the down arrow, and select a column from the list.</span></span> <span data-ttu-id="796e2-125">Se o modelo for um modelo de clustering, selecione **#Cluster** para indicar que o modelo não tem um atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="796e2-125">If the model is a clustering model, select **#Cluster** to indicate that the model does not have a predictable attribute.</span></span> <span data-ttu-id="796e2-126">Note que o valor, **#Cluster**, está disponível somente quando a estrutura de mineração não oferece suporte a outros tipos de atributos previsíveis.</span><span class="sxs-lookup"><span data-stu-id="796e2-126">Note that the value, **#Cluster**, is available only when the mining structure does not support other types of predictable attributes.</span></span>  
  
     <span data-ttu-id="796e2-127">Você pode selecionar apenas um atributo previsível por relatório.</span><span class="sxs-lookup"><span data-stu-id="796e2-127">You can select only one predictable attribute per report.</span></span> <span data-ttu-id="796e2-128">Por padrão, todos os modelos relacionados que têm o mesmo atributo previsível são incluídos no relatório.</span><span class="sxs-lookup"><span data-stu-id="796e2-128">By default, all related models that have the same predictable attribute are included in the report.</span></span>  
  
3.  <span data-ttu-id="796e2-129">Em **Máx. de Casos**, digite um número grande o suficiente para fornecer um exemplo representativo dos dados quando eles forem divididos entre números especificados de dobras.</span><span class="sxs-lookup"><span data-stu-id="796e2-129">For **Max Cases**, type a number that is large enough to provide a representative sample of data when the data is split among the specified number of folds.</span></span> <span data-ttu-id="796e2-130">Se o número for maior que a contagem de casos no conjunto de treinamento do modelo, todos os casos serão usados.</span><span class="sxs-lookup"><span data-stu-id="796e2-130">If the number is greater than the count of cases in the model training set, all cases will be used.</span></span>  
  
     <span data-ttu-id="796e2-131">Se o conjunto de dados de treinamento for muito grande, a configuração do valor de **Máx. de Casos** limitará o número total de casos processados e permitirá que o relatório seja concluído mais rapidamente.</span><span class="sxs-lookup"><span data-stu-id="796e2-131">If the training data set is very large, setting the value for **Max Cases** limits the total number of cases processed, and lets the report finish faster.</span></span> <span data-ttu-id="796e2-132">Porém, você não deve definir **Máx. de Casos** como um valor muito baixo, pois pode haver dados insuficientes para validação cruzada.</span><span class="sxs-lookup"><span data-stu-id="796e2-132">However, you should not set **Max Cases** too low or there may be insufficient data for cross-validation.</span></span>  
  
4.  <span data-ttu-id="796e2-133">Como opção, para **Estado de Destino**, digite o valor do atributo previsível que você quer modelar.</span><span class="sxs-lookup"><span data-stu-id="796e2-133">Optionally, for **Target State**, type the value of the predictable attribute that you want to model.</span></span> <span data-ttu-id="796e2-134">Por exemplo, se a coluna [Bike Buyer] tiver dois valores possíveis, 1 (Sim) e 2 (Não), você poderá inserir o valor 1 para avaliar a precisão do modelo para apenas o resultado desejado.</span><span class="sxs-lookup"><span data-stu-id="796e2-134">For example, if the column [Bike Buyer] has two possible values, 1 (Yes) and 2 (No), you can enter the value 1 to assess the accuracy of the model for just the desired outcome.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="796e2-135"> Se você não digitar um valor, a opção **Limite de Destino** não estará disponível e o modelo será avaliado por todos os valores possível do atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="796e2-135">If you do not enter a value, the **Target Threshold** option is not available, and the model is assessed for all possible values of the predictable attribute.</span></span>  
  
5.  <span data-ttu-id="796e2-136">Como opção, em **Limite de Destino**, digite um número decimal entre 0 e 1 para especificar a probabilidade mínima que uma previsão deve ter para ser considerada precisa.</span><span class="sxs-lookup"><span data-stu-id="796e2-136">Optionally, for **Target Threshold**, type a decimal number between 0 and 1 to specify the minimum probability that a prediction must have to be counted as accurate.</span></span>  
  
     <span data-ttu-id="796e2-137">Para obter dicas adicionais sobre como definir limites de probabilidade, consulte [Medidas no relatório de validação cruzada](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="796e2-137">For additional tips about how to set probability thresholds, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
6.  <span data-ttu-id="796e2-138">Clique em **Obter Resultados**.</span><span class="sxs-lookup"><span data-stu-id="796e2-138">Click **Get Results**.</span></span>  
  
### <a name="print-the-cross-validation-report"></a><span data-ttu-id="796e2-139">Imprimir o relatório de validação cruzada</span><span class="sxs-lookup"><span data-stu-id="796e2-139">Print the cross-validation report</span></span>  
  
1.  <span data-ttu-id="796e2-140">Clique com o botão direito do mouse no relatório completo na guia **Validação Cruzada** .</span><span class="sxs-lookup"><span data-stu-id="796e2-140">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="796e2-141">No menu de atalho, selecione **Imprimir** ou **Visualizar Impressão** para revisar o primeiro relatório.</span><span class="sxs-lookup"><span data-stu-id="796e2-141">In the shortcut menu, select **Print** or **Print Preview** to review the report first.</span></span>  
  
### <a name="create-a-copy-of-the-report-in-microsoft-excel"></a><span data-ttu-id="796e2-142">Criar uma cópia do relatório no Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="796e2-142">Create a copy of the report in Microsoft Excel</span></span>  
  
1.  <span data-ttu-id="796e2-143">Clique com o botão direito do mouse no relatório completo na guia **Validação Cruzada** .</span><span class="sxs-lookup"><span data-stu-id="796e2-143">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="796e2-144">No menu de atalho, selecione **Selecionar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="796e2-144">In the shortcut menu, select **Select All**.</span></span>  
  
3.  <span data-ttu-id="796e2-145">Clique com o botão direito do mouse no texto selecionado e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="796e2-145">Right-click the selected text, and select **Copy**.</span></span>  
  
4.  <span data-ttu-id="796e2-146">Cole a seleção em uma pasta do Excel aberta.</span><span class="sxs-lookup"><span data-stu-id="796e2-146">Paste the selection into an open Excel workbook.</span></span> <span data-ttu-id="796e2-147">Se você usar a opção **Colar** , o relatório será colado no Excel como HTML, preservando a formatação de linhas e colunas.</span><span class="sxs-lookup"><span data-stu-id="796e2-147">If you use the **Paste** option, the report is pasted into Excel as HTML, which preserves row and column formatting.</span></span> <span data-ttu-id="796e2-148">Se colar o relatório usando a opção **Colar Especial** para texto ou texto Unicode, o relatório será colado em um formato delimitado por linha.</span><span class="sxs-lookup"><span data-stu-id="796e2-148">If you paste the report by using the **Paste Special** options for text or Unicode text, the report is pasted in row-delimited format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="796e2-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="796e2-149">See Also</span></span>  
 [<span data-ttu-id="796e2-150">Medidas no relatório de validação cruzada</span><span class="sxs-lookup"><span data-stu-id="796e2-150">Measures in the Cross-Validation Report</span></span>](measures-in-the-cross-validation-report.md)  
  
  
