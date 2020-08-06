---
title: Transformação Dinâmica | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.pivottrans.f1
helpviewer_keywords:
- Pivot transformation
- normalized data [Integration Services]
- PivotUsage property
- datasets [Integration Services], normalized data
- less normalized data set [Integration Services]
ms.assetid: 55f5db6e-6777-435f-8a06-b68c129f8437
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43bdc5be709ea00d4be4601f52c38e96fe3f1ce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686351"
---
# <a name="pivot-transformation"></a><span data-ttu-id="ac33c-102">transformação Dinâmica</span><span class="sxs-lookup"><span data-stu-id="ac33c-102">Pivot Transformation</span></span>
  <span data-ttu-id="ac33c-103">A transformação Dinâmica transforma um conjunto de dados normalizado em um conjunto menos normalizado, em uma versão mais compacta, tornando dinâmicos os dados de entrada em um valor de coluna.</span><span class="sxs-lookup"><span data-stu-id="ac33c-103">The Pivot transformation makes a normalized data set into a less normalized but more compact version by pivoting the input data on a column value.</span></span> <span data-ttu-id="ac33c-104">Por exemplo, um conjunto de dados **Orders** normalizado que lista nome de cliente, produto e quantidade adquirida normalmente tem várias linhas para qualquer cliente que tenha comprado diversos produtos, sendo que cada linha daquele cliente apresenta detalhes do pedido para um produto diferente.</span><span class="sxs-lookup"><span data-stu-id="ac33c-104">For example, a normalized **Orders** data set that lists customer name, product, and quantity purchased typically has multiple rows for any customer who purchased multiple products, with each row for that customer showing order details for a different product.</span></span> <span data-ttu-id="ac33c-105">Ao dinamizar o conjunto de dados na coluna de produto, a transformação dinâmica pode produzir um conjunto de dados com uma única linha por cliente.</span><span class="sxs-lookup"><span data-stu-id="ac33c-105">By pivoting the data set on the product column, the Pivot transformation can output a data set with a single row per customer.</span></span> <span data-ttu-id="ac33c-106">Aquela única linha lista todas as compras realizadas pelo cliente, com os nomes de produto mostrados como nomes de coluna, e a quantidade exibida como um valor na coluna de produto.</span><span class="sxs-lookup"><span data-stu-id="ac33c-106">That single row lists all the purchases by the customer, with the product names shown as column names, and the quantity shown as a value in the product column.</span></span> <span data-ttu-id="ac33c-107">Como nem todo cliente compra todos os produtos, muitas colunas podem conter valores nulos.</span><span class="sxs-lookup"><span data-stu-id="ac33c-107">Because not every customer purchases every product, many columns may contain null values.</span></span>  
  
 <span data-ttu-id="ac33c-108">Quando um conjunto de dados é dinamizado, as colunas de entrada executam funções diferentes no processo de dinamização.</span><span class="sxs-lookup"><span data-stu-id="ac33c-108">When a dataset is pivoted, input columns perform different roles in the pivoting process.</span></span> <span data-ttu-id="ac33c-109">Uma coluna pode participar dos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="ac33c-109">A column can participate in the following ways:</span></span>  
  
-   <span data-ttu-id="ac33c-110">A coluna é passada inalterada até a saída.</span><span class="sxs-lookup"><span data-stu-id="ac33c-110">The column is passed through unchanged to the output.</span></span> <span data-ttu-id="ac33c-111">Como muitas linhas de entrada só podem resultar em uma linha de saída, a transformação copia só o primeiro valor de entrada para a coluna.</span><span class="sxs-lookup"><span data-stu-id="ac33c-111">Because many input rows can result only in one output row, the transformation copies only the first input value for the column.</span></span>  
  
-   <span data-ttu-id="ac33c-112">A coluna age como a chave ou parte da chave que identifica um conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="ac33c-112">The column acts as the key or part of the key that identifies a set of records.</span></span>  
  
-   <span data-ttu-id="ac33c-113">A coluna define a dinamização.</span><span class="sxs-lookup"><span data-stu-id="ac33c-113">The column defines the pivot.</span></span> <span data-ttu-id="ac33c-114">Os valores nesta coluna são associados com colunas no conjunto de dados dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="ac33c-114">The values in this column are associated with columns in the pivoted dataset.</span></span>  
  
-   <span data-ttu-id="ac33c-115">A coluna contém valores que são colocados nas colunas criadas pela dinamização.</span><span class="sxs-lookup"><span data-stu-id="ac33c-115">The column contains values that are placed in the columns that the pivot creates.</span></span>  
  
 <span data-ttu-id="ac33c-116">Essa transformação tem uma entrada, uma saída comum e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="ac33c-116">This transformation has one input, one regular output, and one error output.</span></span>  
  
## <a name="sort-and-duplicate-rows"></a><span data-ttu-id="ac33c-117">Classificar e duplicar linhas</span><span class="sxs-lookup"><span data-stu-id="ac33c-117">Sort and Duplicate Rows</span></span>  
 <span data-ttu-id="ac33c-118">Para dinamizar os dados com eficiência, o que significa criar o mínimo possível de registros no conjunto de dados de saída, os dados de entrada devem ser classificados na coluna dinâmica.</span><span class="sxs-lookup"><span data-stu-id="ac33c-118">To pivot data efficiently, which means creating as few records in the output dataset as possible, the input data must be sorted on the pivot column.</span></span> <span data-ttu-id="ac33c-119">Se os dados não fossem classificados, a transformação dinâmica poderia gerar vários registros para cada valor na chave definida, que é a coluna que define a associação de conjunto.</span><span class="sxs-lookup"><span data-stu-id="ac33c-119">If the data is not sorted, the Pivot transformation might generate multiple records for each value in the set key, which is the column that defines set membership.</span></span> <span data-ttu-id="ac33c-120">Por exemplo, se um conjunto de dados fosse dinamizado em uma coluna **Name** , mas os nomes não fossem classificados, o conjunto de dados de saída poderia ter mais de uma linha para cada cliente, porque uma dinamização ocorre toda vez que o valor **Name** é alterado.</span><span class="sxs-lookup"><span data-stu-id="ac33c-120">For example, if a dataset is pivoted on a **Name** column but the names are not sorted, the output dataset could have more than one row for each customer, because a pivot occurs every time that the value in **Name** changes.</span></span>  
  
 <span data-ttu-id="ac33c-121">Os dados de entrada poderiam conter linhas duplicadas que causarão uma falha na transformação dinâmica.</span><span class="sxs-lookup"><span data-stu-id="ac33c-121">The input data might contain duplicate rows, which will cause the Pivot transformation to fail.</span></span> <span data-ttu-id="ac33c-122">"Linhas duplicadas" significam linhas que têm os mesmos valores nas colunas de chave definidas e nas colunas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="ac33c-122">"Duplicate rows" means rows that have the same values in the set key columns and the pivot columns.</span></span> <span data-ttu-id="ac33c-123">Para evitar uma falha, você pode configurar a transformação para redirecionar linhas de erro para uma saída de erro ou pode pré-agregar valores para ter certeza de que não existem linhas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="ac33c-123">To avoid failure, you can either configure the transformation to redirect error rows to an error output or you can pre-aggregate values to ensure there are no duplicate rows.</span></span>  
  
##  <a name="options-in-the-pivot-dialog-box"></a><a name="options"></a> <span data-ttu-id="ac33c-124">Opções da caixa de diálogo Dinâmica</span><span class="sxs-lookup"><span data-stu-id="ac33c-124">Options in the Pivot Dialog Box</span></span>  
 <span data-ttu-id="ac33c-125">Você configura a operação dinâmica definindo as opções na caixa de diálogo **Dinâmica** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-125">You configure the pivot operation by setting the options in the **Pivot** dialog box.</span></span> <span data-ttu-id="ac33c-126">Para abrir a caixa de diálogo **Dinâmica** , adicione a transformação Dinâmica ao pacote no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]e clique com o botão direito do mouse no componente e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ac33c-126">To open the **Pivot** dialog box, add the Pivot transformation to the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and then right-click the component and click **Edit**.</span></span>  
  
 <span data-ttu-id="ac33c-127">A lista a seguir descreve as opções da caixa de diálogo **Dinâmica** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-127">The following list describes the options in the **Pivot** dialog box.</span></span>  
  
 <span data-ttu-id="ac33c-128">**Chave Dinâmica**</span><span class="sxs-lookup"><span data-stu-id="ac33c-128">**Pivot Key**</span></span>  
 <span data-ttu-id="ac33c-129">Especifica a coluna a ser usada para obter valores na linha superior (linha de cabeçalho) da tabela.</span><span class="sxs-lookup"><span data-stu-id="ac33c-129">Specifies the column to use for values across the top row (header row) of the table.</span></span>  
  
 <span data-ttu-id="ac33c-130">**Definir Chave**</span><span class="sxs-lookup"><span data-stu-id="ac33c-130">**Set Key**</span></span>  
 <span data-ttu-id="ac33c-131">Especifica a coluna a ser usada para obter valores na coluna esquerda da tabela.</span><span class="sxs-lookup"><span data-stu-id="ac33c-131">Specifies the column to use for values in the left column of the table.</span></span> <span data-ttu-id="ac33c-132">A data de entrada deve ser classificada nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="ac33c-132">The input date must be sorted on this column.</span></span>  
  
 <span data-ttu-id="ac33c-133">**Valor Dinâmico**</span><span class="sxs-lookup"><span data-stu-id="ac33c-133">**Pivot Value**</span></span>  
 <span data-ttu-id="ac33c-134">Especifica a coluna a ser usada para obter os valores da tabela, que não sejam os valores da linha do cabeçalho e da coluna esquerda.</span><span class="sxs-lookup"><span data-stu-id="ac33c-134">Specifies the column to use for the table values, other than the values in the header row and the left column.</span></span>  
  
 <span data-ttu-id="ac33c-135">**Ignorar valores de Chave Dinâmica não correspondentes e relatá-los após a execução de DataFlow**</span><span class="sxs-lookup"><span data-stu-id="ac33c-135">**Ignore un-matched Pivot Key values and report them after DataFlow execution**</span></span>  
 <span data-ttu-id="ac33c-136">Selecione essa opção para configurar a transformação Dinâmica para ignorar as linhas que contêm valores não reconhecidos na coluna **Chave Dinâmica** e gerar todos os valores de chave dinâmica para uma mensagem de log, quando o pacote é executado.</span><span class="sxs-lookup"><span data-stu-id="ac33c-136">Select this option to configure the Pivot transformation to ignore rows containing unrecognized values in the **Pivot Key** column and to output all of the pivot key values to a log message, when the package is run.</span></span>  
  
 <span data-ttu-id="ac33c-137">Você também pode configurar a transformação para gerar os valores definindo a propriedade personalizada `PassThroughUnmatchedPivotKeys` como `True`.</span><span class="sxs-lookup"><span data-stu-id="ac33c-137">You can also configure the transformation to output the values by setting the `PassThroughUnmatchedPivotKeys` custom property to `True`.</span></span>  
  
 <span data-ttu-id="ac33c-138">**Gerar colunas de saída dinâmica a partir de valores**</span><span class="sxs-lookup"><span data-stu-id="ac33c-138">**Generate pivot output columns from values**</span></span>  
 <span data-ttu-id="ac33c-139">Digite os valores de chave dinâmica nesta caixa para permitir que a transformação Dinâmica crie colunas de saída para cada valor.</span><span class="sxs-lookup"><span data-stu-id="ac33c-139">Enter the pivot key values in this box to enable the Pivot transformation to create output columns for each value.</span></span> <span data-ttu-id="ac33c-140">Você pode inserir os valores antes de executar o pacote ou fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ac33c-140">You can either enter the values prior to running the package, or do the following.</span></span>  
  
1.  <span data-ttu-id="ac33c-141">Selecione a opção **Ignorar valores de Chave Dinâmica não correspondentes e relatá-los após a execução de DataFlow** e clique em **OK** na caixa de diálogo **Dinâmica** para salvar as alterações à transformação Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="ac33c-141">Select the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then click **OK** in the **Pivot** dialog box to save the changes to the Pivot transformation.</span></span>  
  
2.  <span data-ttu-id="ac33c-142">Execute o pacote.</span><span class="sxs-lookup"><span data-stu-id="ac33c-142">Run the package.</span></span>  
  
3.  <span data-ttu-id="ac33c-143">Quando o pacote tiver êxito, clique na guia **Progresso** e procure a mensagem de log de informações da transformação Dinâmica que contém os valores de chave dinâmica.</span><span class="sxs-lookup"><span data-stu-id="ac33c-143">When the package succeeds, click the **Progress** tab and look for the information log message from the Pivot transformation that contains the pivot key values.</span></span>  
  
4.  <span data-ttu-id="ac33c-144">Clique com o botão direito do mouse na mensagem e clique em **Copiar Texto de Mensagem**.</span><span class="sxs-lookup"><span data-stu-id="ac33c-144">Right-click the message and click **Copy Message Text**.</span></span>  
  
5.  <span data-ttu-id="ac33c-145">Clique em **Parar Depuração** no menu **Depurar** para alternar para o modo de design.</span><span class="sxs-lookup"><span data-stu-id="ac33c-145">Click **Stop Debugging** on the **Debug** menu to switch to the design mode.</span></span>  
  
6.  <span data-ttu-id="ac33c-146">Clique com o botão direito do mouse na transformação Dinâmica e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ac33c-146">Right-click the Pivot transformation, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="ac33c-147">Desmarque a opção **Ignorar valores de Chave Dinâmica não correspondentes e relatá-los após a execução de DataFlow** e cole os valores de chave dinâmica na caixa de diálogo **Gerar colunas de saída dinâmicas a partir dos valores** usando o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="ac33c-147">Uncheck the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then paste the pivot key values in the **Generate pivot output columns from values** box using the following format.</span></span>  
  
     <span data-ttu-id="ac33c-148">[valor1],[valor2],[valor3]</span><span class="sxs-lookup"><span data-stu-id="ac33c-148">[value1],[value2],[value3]</span></span>  
  
 <span data-ttu-id="ac33c-149">**Gerar Colunas Agora**</span><span class="sxs-lookup"><span data-stu-id="ac33c-149">**Generate Columns Now**</span></span>  
 <span data-ttu-id="ac33c-150">Clique para criar uma coluna de saída para cada valor de chave dinâmica listada na caixa **Gerar colunas de saída dinâmicas a partir dos valores** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-150">Click to create an output column for each pivot key value that is listed in the **Generate pivot output columns from values** box.</span></span>  
  
 <span data-ttu-id="ac33c-151">As colunas de saída aparecem na caixa **Colunas de saída dinâmicas existentes** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-151">The output columns appear in the **Existing pivoted output columns** box.</span></span>  
  
 <span data-ttu-id="ac33c-152">**Colunas de saída dinâmicas existentes**</span><span class="sxs-lookup"><span data-stu-id="ac33c-152">**Existing pivoted output columns**</span></span>  
 <span data-ttu-id="ac33c-153">Lista as colunas de saída para os valores de chave dinâmica.</span><span class="sxs-lookup"><span data-stu-id="ac33c-153">Lists the output columns for the pivot key values</span></span>  
  
 <span data-ttu-id="ac33c-154">A tabela a seguir mostra um conjunto de dados após a dinamização dos dados na coluna **Ano** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-154">The following table shows a data set before the data is pivoted on the **Year** column.</span></span>  
  
|<span data-ttu-id="ac33c-155">Ano</span><span class="sxs-lookup"><span data-stu-id="ac33c-155">Year</span></span>|<span data-ttu-id="ac33c-156">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ac33c-156">Product Name</span></span>|<span data-ttu-id="ac33c-157">Total</span><span class="sxs-lookup"><span data-stu-id="ac33c-157">Total</span></span>|  
|----------|------------------|-----------|  
|<span data-ttu-id="ac33c-158">2004</span><span class="sxs-lookup"><span data-stu-id="ac33c-158">2004</span></span>|<span data-ttu-id="ac33c-159">HL Mountain Tire</span><span class="sxs-lookup"><span data-stu-id="ac33c-159">HL Mountain Tire</span></span>|<span data-ttu-id="ac33c-160">1504884.15</span><span class="sxs-lookup"><span data-stu-id="ac33c-160">1504884.15</span></span>|  
|<span data-ttu-id="ac33c-161">2003</span><span class="sxs-lookup"><span data-stu-id="ac33c-161">2003</span></span>|<span data-ttu-id="ac33c-162">Tubo de pneu de estrada</span><span class="sxs-lookup"><span data-stu-id="ac33c-162">Road Tire Tube</span></span>|<span data-ttu-id="ac33c-163">35920.50</span><span class="sxs-lookup"><span data-stu-id="ac33c-163">35920.50</span></span>|  
|<span data-ttu-id="ac33c-164">2004</span><span class="sxs-lookup"><span data-stu-id="ac33c-164">2004</span></span>|<span data-ttu-id="ac33c-165">Garrafa de Água – 887 ml</span><span class="sxs-lookup"><span data-stu-id="ac33c-165">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="ac33c-166">2805.00</span><span class="sxs-lookup"><span data-stu-id="ac33c-166">2805.00</span></span>|  
|<span data-ttu-id="ac33c-167">2002</span><span class="sxs-lookup"><span data-stu-id="ac33c-167">2002</span></span>|<span data-ttu-id="ac33c-168">Pneu de Passeio</span><span class="sxs-lookup"><span data-stu-id="ac33c-168">Touring Tire</span></span>|<span data-ttu-id="ac33c-169">62364.225</span><span class="sxs-lookup"><span data-stu-id="ac33c-169">62364.225</span></span>|  
  
 <span data-ttu-id="ac33c-170">A tabela a seguir mostra um conjunto de dados depois de os dados serem dinamizados na coluna **Ano** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-170">The following table shows a data set after the data has been pivoted on the **Year** column.</span></span>  
  
||<span data-ttu-id="ac33c-171">2002</span><span class="sxs-lookup"><span data-stu-id="ac33c-171">2002</span></span>|<span data-ttu-id="ac33c-172">2003</span><span class="sxs-lookup"><span data-stu-id="ac33c-172">2003</span></span>|<span data-ttu-id="ac33c-173">2004</span><span class="sxs-lookup"><span data-stu-id="ac33c-173">2004</span></span>|  
|-|----------|----------|----------|  
|<span data-ttu-id="ac33c-174">HL Mountain Tire</span><span class="sxs-lookup"><span data-stu-id="ac33c-174">HL Mountain Tire</span></span>|<span data-ttu-id="ac33c-175">141164.10</span><span class="sxs-lookup"><span data-stu-id="ac33c-175">141164.10</span></span>|<span data-ttu-id="ac33c-176">446297.775</span><span class="sxs-lookup"><span data-stu-id="ac33c-176">446297.775</span></span>|<span data-ttu-id="ac33c-177">1504884.15</span><span class="sxs-lookup"><span data-stu-id="ac33c-177">1504884.15</span></span>|  
|<span data-ttu-id="ac33c-178">Tubo de pneu de estrada</span><span class="sxs-lookup"><span data-stu-id="ac33c-178">Road Tire Tube</span></span>|<span data-ttu-id="ac33c-179">3592.05</span><span class="sxs-lookup"><span data-stu-id="ac33c-179">3592.05</span></span>|<span data-ttu-id="ac33c-180">35920.50</span><span class="sxs-lookup"><span data-stu-id="ac33c-180">35920.50</span></span>|<span data-ttu-id="ac33c-181">89801.25</span><span class="sxs-lookup"><span data-stu-id="ac33c-181">89801.25</span></span>|  
|<span data-ttu-id="ac33c-182">Garrafa de Água – 887 ml</span><span class="sxs-lookup"><span data-stu-id="ac33c-182">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="ac33c-183">*NULL*</span><span class="sxs-lookup"><span data-stu-id="ac33c-183">*NULL*</span></span>|<span data-ttu-id="ac33c-184">*NULL*</span><span class="sxs-lookup"><span data-stu-id="ac33c-184">*NULL*</span></span>|<span data-ttu-id="ac33c-185">2805.00</span><span class="sxs-lookup"><span data-stu-id="ac33c-185">2805.00</span></span>|  
|<span data-ttu-id="ac33c-186">Pneu de Passeio</span><span class="sxs-lookup"><span data-stu-id="ac33c-186">Touring Tire</span></span>|<span data-ttu-id="ac33c-187">62364.225</span><span class="sxs-lookup"><span data-stu-id="ac33c-187">62364.225</span></span>|<span data-ttu-id="ac33c-188">375051.60</span><span class="sxs-lookup"><span data-stu-id="ac33c-188">375051.60</span></span>|<span data-ttu-id="ac33c-189">1041810.00</span><span class="sxs-lookup"><span data-stu-id="ac33c-189">1041810.00</span></span>|  
  
 <span data-ttu-id="ac33c-190">Para dinamizar os dados na coluna **Ano** , como mostrado acima, as opções a seguir são definidas na caixa de diálogo **Dinâmica** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-190">To pivot the data on the **Year** column, as shown above, the following options are set in the **Pivot** dialog box.</span></span>  
  
-   <span data-ttu-id="ac33c-191">Ano é selecionado na caixa de listagem **Chave Dinâmica** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-191">Year is selected in the **Pivot Key** list box.</span></span>  
  
-   <span data-ttu-id="ac33c-192">O nome do produto é selecionado na caixa de listagem **Definir Chave** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-192">Product Name is selected in the **Set Key** list box.</span></span>  
  
-   <span data-ttu-id="ac33c-193">Total é selecionado na caixa de listagem **Valor Dinâmico** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-193">Total is selected in the **Pivot Value** list box.</span></span>  
  
-   <span data-ttu-id="ac33c-194">Os valores a seguir são inseridos na caixa **Gerar colunas de saída dinâmicas a partir dos valores** .</span><span class="sxs-lookup"><span data-stu-id="ac33c-194">The following values are entered in the **Generate pivot output columns from values** box.</span></span>  
  
     <span data-ttu-id="ac33c-195">[2002],[2003],[2004]</span><span class="sxs-lookup"><span data-stu-id="ac33c-195">[2002],[2003],[2004]</span></span>  
  
## <a name="configuration-of-the-pivot-transformation"></a><span data-ttu-id="ac33c-196">Configuração da Transformação Dinâmica</span><span class="sxs-lookup"><span data-stu-id="ac33c-196">Configuration of the Pivot Transformation</span></span>  
 <span data-ttu-id="ac33c-197">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="ac33c-197">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ac33c-198">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** , clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ac33c-198">For more information about the properties that you can set in the **Advanced Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ac33c-199">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="ac33c-199">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="ac33c-200">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="ac33c-200">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-content"></a><span data-ttu-id="ac33c-201">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="ac33c-201">Related Content</span></span>  
 <span data-ttu-id="ac33c-202">Para obter informações sobre como definir as propriedades desse componente, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ac33c-202">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac33c-203">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ac33c-203">See Also</span></span>  
 <span data-ttu-id="ac33c-204">[Transformação não dinâmica](pivot-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="ac33c-204">[Unpivot Transformation](pivot-transformation.md) </span></span>  
 <span data-ttu-id="ac33c-205">[Fluxo de Dados](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="ac33c-205">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="ac33c-206">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="ac33c-206">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
