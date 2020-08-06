---
title: Desabilitar a compactação em uma tabela ou índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data compression [SQL Server], disabling
ms.assetid: bda1e452-397b-4757-82a4-181217361589
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 80b5775d3b6f7a3f47ab75c5348b556c17b6e676
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581952"
---
# <a name="disable-compression-on-a-table-or-index"></a><span data-ttu-id="662f3-102">Desabilitar a compactação em uma tabela ou índice</span><span class="sxs-lookup"><span data-stu-id="662f3-102">Disable Compression on a Table or Index</span></span>
  <span data-ttu-id="662f3-103">Este tópico descreve como desabilitar a compactação em uma tabela ou índice no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="662f3-103">This topic describes how to disable compression on a table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="662f3-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="662f3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="662f3-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="662f3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="662f3-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="662f3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="662f3-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="662f3-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="662f3-108">**Para desabilitar a compactação em uma tabela ou índice, usando:**</span><span class="sxs-lookup"><span data-stu-id="662f3-108">**To disable compression on a table or index, using:**</span></span>  
  
     [<span data-ttu-id="662f3-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="662f3-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="662f3-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="662f3-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="662f3-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="662f3-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="662f3-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="662f3-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="662f3-113">Se a tabela for um heap, a operação de reconstrução para o modo ONLINE será um thread único.</span><span class="sxs-lookup"><span data-stu-id="662f3-113">If the table is a heap, the rebuild operation for ONLINE mode will be single threaded.</span></span> <span data-ttu-id="662f3-114">Use o modo OFFLINE para uma operação de reconstrução de um heap multi-threaded.</span><span class="sxs-lookup"><span data-stu-id="662f3-114">Use OFFLINE mode for a multi-threaded heap rebuild operation.</span></span> <span data-ttu-id="662f3-115">Para obter mais informações sobre compactação de dados, veja [Compactação de dados](data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="662f3-115">For a more information about data compression, see [Data Compression](data-compression.md).</span></span>  
  
-   <span data-ttu-id="662f3-116">Para avaliar como a alteração do estado de compactação afetará uma tabela, um índice ou uma partição, use o procedimento armazenado [sp_estimate_data_compression_savings](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="662f3-116">To evaluate how changing the compression state will affect a table, an index, or a partition, use the [sp_estimate_data_compression_savings](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) stored procedure.</span></span>  
  
-   <span data-ttu-id="662f3-117">Não será possível alterar a configuração de compactação de uma única partição se a tabela tiver índices não alinhados.</span><span class="sxs-lookup"><span data-stu-id="662f3-117">You cannot change the compression setting of a single partition if the table has nonaligned indexes.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="662f3-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="662f3-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="662f3-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="662f3-119">Permissions</span></span>  
 <span data-ttu-id="662f3-120">Requer a permissão ALTER na tabela ou índice.</span><span class="sxs-lookup"><span data-stu-id="662f3-120">Requires ALTER permission on the table or index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="662f3-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="662f3-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-compression-on-a-table"></a><span data-ttu-id="662f3-122">Para desabilitar a compactação em uma tabela</span><span class="sxs-lookup"><span data-stu-id="662f3-122">To disable compression on a table</span></span>  
  
1.  <span data-ttu-id="662f3-123">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela na qual você deseja desabilitar a compactação e expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="662f3-123">In Object Explorer, expand the database that contains the table on which you want to disable compression and then expand the **Tables** folder.</span></span>  
  
2.  <span data-ttu-id="662f3-124">Clique com o botão direito do mouse na tabela ou índice no qual você deseja desabilitar a compactação, aponte para **Repositório** e selecione **Gerenciar Compactação...** .</span><span class="sxs-lookup"><span data-stu-id="662f3-124">Right-click the table or index on which you want to disable compression, point to **Storage** and select **Manage Compression...**.</span></span>  
  
3.  <span data-ttu-id="662f3-125">Para desabilitar a compactação em um índice, expanda a tabela que contém o índice que você deseja expandir e expanda a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="662f3-125">To disable compression on an index, expand the table that contains the index and then expand the **Indexes** folder.</span></span>  
  
4.  <span data-ttu-id="662f3-126">No Assistente de Compactação de Dados, na página **Bem-vindo ao Assistente de Compactação de Dados** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="662f3-126">In the Data Compression Wizard, on the **Welcome to the Data Compression Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="662f3-127">Na página **Selecionar Tipo de Compactação** , selecione **Nenhum** como o tipo de compactação a ser aplicado a cada partição no índice no qual você desabilitar a compactação.</span><span class="sxs-lookup"><span data-stu-id="662f3-127">On the **Select Compression Type** page, select **None** as the compression type to apply to each partition in the index on which you want to disable compression.</span></span> <span data-ttu-id="662f3-128">Ao concluir, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="662f3-128">When finished, click **Next**.</span></span>  
  
     <span data-ttu-id="662f3-129">As seguintes opções estão disponíveis na página **Selecionar Tipo de Compactação** :</span><span class="sxs-lookup"><span data-stu-id="662f3-129">The following options are available on the **Select Compression Type** page:</span></span>  
  
     <span data-ttu-id="662f3-130">Caixa de seleção**Usar o mesmo tipo de compactação para todas as partições**</span><span class="sxs-lookup"><span data-stu-id="662f3-130">**Use the same compression type for all partitions** check box</span></span>  
     <span data-ttu-id="662f3-131">Selecione para configurar a mesma configuração de compactação para todas as partições.</span><span class="sxs-lookup"><span data-stu-id="662f3-131">Select to configure the same compression setting for all partitions.</span></span> <span data-ttu-id="662f3-132">Isso habilita a caixa de seleção e desabilita a coluna **Tipo de Compactação** na grade.</span><span class="sxs-lookup"><span data-stu-id="662f3-132">This enables the selection box and disables the **Compression Type** column in the grid.</span></span> <span data-ttu-id="662f3-133">Quando selecionadas, as opções na lista adjacente são **Nenhum**, **Linha**e **Página**.</span><span class="sxs-lookup"><span data-stu-id="662f3-133">When selected, the options in the adjacent list are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="662f3-134">**Número da partição**</span><span class="sxs-lookup"><span data-stu-id="662f3-134">**Partition Number**</span></span>  
     <span data-ttu-id="662f3-135">Lista cada partição na tabela ou índice.</span><span class="sxs-lookup"><span data-stu-id="662f3-135">Lists each partition in the table or index.</span></span> <span data-ttu-id="662f3-136">Essa coluna é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="662f3-136">This column is read-only.</span></span>  
  
     <span data-ttu-id="662f3-137">**Tipo de Compactação**</span><span class="sxs-lookup"><span data-stu-id="662f3-137">**Compression Type**</span></span>  
     <span data-ttu-id="662f3-138">Selecione a opção de compactação para cada partição.</span><span class="sxs-lookup"><span data-stu-id="662f3-138">Select the compression option for each partition.</span></span> <span data-ttu-id="662f3-139">Ela não estará disponível quando a opção **Usar o mesmo tipo de compactação para todas as partições** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="662f3-139">Is not available when **Use the same compression type for all partitions** is selected.</span></span> <span data-ttu-id="662f3-140">As opções da lista são **Nenhum**, **Linha**e **Página**.</span><span class="sxs-lookup"><span data-stu-id="662f3-140">List options are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="662f3-141">**Limite**</span><span class="sxs-lookup"><span data-stu-id="662f3-141">**Boundary**</span></span>  
     <span data-ttu-id="662f3-142">Exibe o limite da partição.</span><span class="sxs-lookup"><span data-stu-id="662f3-142">Displays the partition boundary.</span></span> <span data-ttu-id="662f3-143">Essa coluna é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="662f3-143">This column is read-only.</span></span>  
  
     <span data-ttu-id="662f3-144">**Contagem de Linhas**</span><span class="sxs-lookup"><span data-stu-id="662f3-144">**Row Count**</span></span>  
     <span data-ttu-id="662f3-145">Exibe o número de linhas nesta partição.</span><span class="sxs-lookup"><span data-stu-id="662f3-145">Displays the number of rows in this partition.</span></span> <span data-ttu-id="662f3-146">Essa coluna é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="662f3-146">This column is read-only.</span></span>  
  
     <span data-ttu-id="662f3-147">**Espaço Atual**</span><span class="sxs-lookup"><span data-stu-id="662f3-147">**Current Space**</span></span>  
     <span data-ttu-id="662f3-148">Exibe o espaço atual ocupado por esta partição em megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="662f3-148">Displays the current space this partition occupies in megabytes (MB).</span></span> <span data-ttu-id="662f3-149">Essa coluna é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="662f3-149">This column is read-only.</span></span>  
  
     <span data-ttu-id="662f3-150">**Espaço Compactado Solicitado**</span><span class="sxs-lookup"><span data-stu-id="662f3-150">**Requested Compressed Space**</span></span>  
     <span data-ttu-id="662f3-151">Depois de clicar em **Calcular**, essa coluna exibe o tamanho estimado de cada partição após a compactação usando a configuração especificada na coluna **Tipo de Compactação** .</span><span class="sxs-lookup"><span data-stu-id="662f3-151">After you click **Calculate**, this column displays the estimated size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span> <span data-ttu-id="662f3-152">Essa coluna é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="662f3-152">This column is read-only.</span></span>  
  
     <span data-ttu-id="662f3-153">**Calcular**</span><span class="sxs-lookup"><span data-stu-id="662f3-153">**Calculate**</span></span>  
     <span data-ttu-id="662f3-154">Clique para estimar o tamanho de cada partição após a compactação usando a configuração especificada na coluna **Tipo de Compactação** .</span><span class="sxs-lookup"><span data-stu-id="662f3-154">Click to estimate the size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span>  
  
6.  <span data-ttu-id="662f3-155">Na página **Selecione uma Opção de Saída** , especifique como você deseja executar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="662f3-155">In the **Select an Output Option** page, specify how you want to complete this task.</span></span> <span data-ttu-id="662f3-156">Selecione **Criar Script** para criar um script SQL baseado nas páginas anteriores no assistente.</span><span class="sxs-lookup"><span data-stu-id="662f3-156">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="662f3-157">Selecione **Executar imediatamente** para criar a nova tabela particionada depois de concluir todas as páginas restantes no assistente.</span><span class="sxs-lookup"><span data-stu-id="662f3-157">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="662f3-158">Selecione **Agenda** para criar uma nova tabela particionada em um momento predeterminado no futuro.</span><span class="sxs-lookup"><span data-stu-id="662f3-158">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="662f3-159">Se você selecionar **Criar script**, as opções a seguir estarão disponíveis em **Opções de script**:</span><span class="sxs-lookup"><span data-stu-id="662f3-159">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="662f3-160">**Script para arquivo**</span><span class="sxs-lookup"><span data-stu-id="662f3-160">**Script to file**</span></span>  
     <span data-ttu-id="662f3-161">Gera o script como um arquivo .sql.</span><span class="sxs-lookup"><span data-stu-id="662f3-161">Generates the script as a .sql file.</span></span> <span data-ttu-id="662f3-162">Digite um nome de arquivo e o local na caixa **Nome do arquivo** ou clique em **Procurar** para abrir a caixa de diálogo **Local do Arquivo de Script** .</span><span class="sxs-lookup"><span data-stu-id="662f3-162">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="662f3-163">Em **Salvar Como**, selecione **Texto Unicode** ou **Texto ANSI**.</span><span class="sxs-lookup"><span data-stu-id="662f3-163">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="662f3-164">**Script para Área de Transferência**</span><span class="sxs-lookup"><span data-stu-id="662f3-164">**Script to Clipboard**</span></span>  
     <span data-ttu-id="662f3-165">Salva o script na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="662f3-165">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="662f3-166">**Script para Nova Janela de Consulta**</span><span class="sxs-lookup"><span data-stu-id="662f3-166">**Script to New Query Window**</span></span>  
     <span data-ttu-id="662f3-167">Gera o script para uma nova janela do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="662f3-167">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="662f3-168">Essa é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="662f3-168">This is the default selection.</span></span>  
  
     <span data-ttu-id="662f3-169">Se você selecionar **Agenda**, clique em **Alterar agenda**.</span><span class="sxs-lookup"><span data-stu-id="662f3-169">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="662f3-170">Na caixa de diálogo **Nova Agenda de Trabalho**, na caixa **Nome**, digite o nome da agenda de trabalho.</span><span class="sxs-lookup"><span data-stu-id="662f3-170">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="662f3-171">Na lista **Tipo de Agenda** , selecione o tipo de agenda:</span><span class="sxs-lookup"><span data-stu-id="662f3-171">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="662f3-172">**Iniciar automaticamente quando o SQL Server Agent for iniciado**</span><span class="sxs-lookup"><span data-stu-id="662f3-172">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="662f3-173">**Iniciar sempre que as CPUs estiverem ociosas**</span><span class="sxs-lookup"><span data-stu-id="662f3-173">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="662f3-174">**Recorrente**.</span><span class="sxs-lookup"><span data-stu-id="662f3-174">**Recurring**.</span></span> <span data-ttu-id="662f3-175">Selecione essa opção se sua nova tabela particionada for atualizada com novas informações regularmente.</span><span class="sxs-lookup"><span data-stu-id="662f3-175">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="662f3-176">**Uma vez**.</span><span class="sxs-lookup"><span data-stu-id="662f3-176">**One time**.</span></span> <span data-ttu-id="662f3-177">Essa é a seleção padrão.</span><span class="sxs-lookup"><span data-stu-id="662f3-177">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="662f3-178">Marque ou desmarque a caixa de seleção **Habilitado** para habilitar ou desabilitar a agenda.</span><span class="sxs-lookup"><span data-stu-id="662f3-178">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="662f3-179">Se você selecionar **Recorrente**:</span><span class="sxs-lookup"><span data-stu-id="662f3-179">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="662f3-180">Em **Frequência**, na lista **Ocorre** , especifique a frequência de ocorrência:</span><span class="sxs-lookup"><span data-stu-id="662f3-180">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="662f3-181">Se você selecionar **Diário**, na caixa **Ocorre periodicamente a cada** , digite a frequência com que a agenda de trabalho se repete em dias.</span><span class="sxs-lookup"><span data-stu-id="662f3-181">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="662f3-182">Se você selecionar **Semanal**, na caixa **Ocorre periodicamente a cada** , digite a frequência com que a agenda de trabalho se repete em semanas.</span><span class="sxs-lookup"><span data-stu-id="662f3-182">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="662f3-183">Selecione o dia ou os dias da semana em que a agenda de trabalho é executada.</span><span class="sxs-lookup"><span data-stu-id="662f3-183">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="662f3-184">Se você selecionar **Mensalmente**, selecione **Dia** ou **O**.</span><span class="sxs-lookup"><span data-stu-id="662f3-184">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="662f3-185">Se você selecionar **Dia**, digite o dia do mês que você deseja que a agenda de trabalho seja executada e a frequência com que a agenda de trabalho se repete em meses.</span><span class="sxs-lookup"><span data-stu-id="662f3-185">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="662f3-186">Por exemplo, se desejar que a agenda de trabalho seja executada no 15º dia do mês a cada dois meses, selecione **Dia** e digite "15" na primeira caixa e "2" na segunda caixa.</span><span class="sxs-lookup"><span data-stu-id="662f3-186">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="662f3-187">Observe que o maior número permitido na segunda caixa é "99".</span><span class="sxs-lookup"><span data-stu-id="662f3-187">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="662f3-188">Se você selecionar **O**, selecione o dia específico da semana no mês que você deseja que a agenda de trabalho seja executada e a frequência com que a agenda de trabalho se repete em meses.</span><span class="sxs-lookup"><span data-stu-id="662f3-188">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="662f3-189">Por exemplo, se você desejar que a agenda de trabalho seja executada no último dia da semana do mês a cada dois meses, selecione **Dia**, selecione **último** na primeira lista e **dia da semana** na segunda lista e depois digite “2” na última caixa.</span><span class="sxs-lookup"><span data-stu-id="662f3-189">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="662f3-190">Você também pode selecionar **primeiro**, **segundo**, **terceiro** ou **quarto**, bem como dias específicos da semana (por exemplo: domingo ou quarta-feira) nas primeiras duas listas.</span><span class="sxs-lookup"><span data-stu-id="662f3-190">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="662f3-191">Observe que o maior número permitido na última caixa é "99".</span><span class="sxs-lookup"><span data-stu-id="662f3-191">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="662f3-192">Em **Frequência diária**, especifique a frequência com que a agenda de trabalho se repete no dia da execução da agenda de trabalho:</span><span class="sxs-lookup"><span data-stu-id="662f3-192">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="662f3-193">Se você selecionar **Ocorre uma vez às**, digite a hora específica do dia em que a agenda de trabalho deve ser executada na caixa **Ocorre uma vez às** .</span><span class="sxs-lookup"><span data-stu-id="662f3-193">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="662f3-194">Digite a hora, os minutos e os segundos do dia, bem como AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="662f3-194">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="662f3-195">Se você selecionar **Ocorre a cada**, especifique a frequência com que a agenda de trabalho é executada durante o dia escolhido em **Frequência**.</span><span class="sxs-lookup"><span data-stu-id="662f3-195">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="662f3-196">Por exemplo, se você desejar que o agendamento de trabalho se repita a cada 2 horas durante o dia em que é executado, selecione **Ocorre a cada**, digite "2" na primeira caixa e selecione **hora(s)** na lista.</span><span class="sxs-lookup"><span data-stu-id="662f3-196">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="662f3-197">Nessa lista, você pode selecionar também **minuto(s)** e **segundo(s)** .</span><span class="sxs-lookup"><span data-stu-id="662f3-197">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="662f3-198">Observe que o maior número permitido na primeira caixa é "100".</span><span class="sxs-lookup"><span data-stu-id="662f3-198">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="662f3-199">Na caixa **Iniciando às** , digite a hora em que a agenda de trabalho deve começar a ser executada.</span><span class="sxs-lookup"><span data-stu-id="662f3-199">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="662f3-200">Na caixa **Terminando às** , digite a hora em que a agenda de trabalho deve parar de se repetir.</span><span class="sxs-lookup"><span data-stu-id="662f3-200">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="662f3-201">Digite a hora, os minutos e os segundos do dia, bem como AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="662f3-201">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="662f3-202">Em **Duração**, em **Data de início**, digite a data que você deseja que a agenda de trabalho inicie a execução.</span><span class="sxs-lookup"><span data-stu-id="662f3-202">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="662f3-203">Selecione **Data de término** ou **Nenhuma data de término** para indicar quando a execução da agenda de trabalho deve parar.</span><span class="sxs-lookup"><span data-stu-id="662f3-203">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="662f3-204">Se você selecionar **Data de término**, digite a data em que você deseja que a execução da agenda de trabalho pare.</span><span class="sxs-lookup"><span data-stu-id="662f3-204">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="662f3-205">Se você selecionar **Uma Vez**, em **Ocorrência única**, na caixa **Data** , insira a data em que o agendamento de trabalho será executado.</span><span class="sxs-lookup"><span data-stu-id="662f3-205">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="662f3-206">Na caixa **Hora** , digite a hora em que a agenda de trabalho será executada.</span><span class="sxs-lookup"><span data-stu-id="662f3-206">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="662f3-207">Digite a hora, os minutos e os segundos do dia, bem como AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="662f3-207">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="662f3-208">Em **Resumo**, em **Descrição**, verifique se todas as configurações da agenda de trabalho estão corretas.</span><span class="sxs-lookup"><span data-stu-id="662f3-208">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="662f3-209">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="662f3-209">Click **OK**.</span></span>  
  
     <span data-ttu-id="662f3-210">Depois de concluir essa página, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="662f3-210">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="662f3-211">Na página **Resumo da Revisão** , em **Examinar as seleções**, expanda todas as opções disponíveis para verificar se todas as configurações estão corretas.</span><span class="sxs-lookup"><span data-stu-id="662f3-211">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all settings are correct.</span></span> <span data-ttu-id="662f3-212">Se tudo estiver como esperado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="662f3-212">If everything is as expected, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="662f3-213">Na página **Progresso do Assistente de Compactação** , monitore as informações de status das ações do Assistente para Criar Partição.</span><span class="sxs-lookup"><span data-stu-id="662f3-213">On the **Compression Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="662f3-214">Dependendo das opções selecionadas no assistente, a página de progresso pode conter uma ou várias ações.</span><span class="sxs-lookup"><span data-stu-id="662f3-214">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="662f3-215">A caixa superior exibe o status geral do assistente e o número de mensagens de status, erro e aviso que ele recebeu.</span><span class="sxs-lookup"><span data-stu-id="662f3-215">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="662f3-216">As opções a seguir estão disponíveis na página **Progresso do Assistente de Compactação** :</span><span class="sxs-lookup"><span data-stu-id="662f3-216">The following options are available on the **Compression Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="662f3-217">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="662f3-217">**Details**</span></span>  
     <span data-ttu-id="662f3-218">Fornece a ação, status e qualquer mensagem retornada pela ação executada pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="662f3-218">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="662f3-219">**Ação**</span><span class="sxs-lookup"><span data-stu-id="662f3-219">**Action**</span></span>  
     <span data-ttu-id="662f3-220">Especifica o tipo e o nome de cada ação.</span><span class="sxs-lookup"><span data-stu-id="662f3-220">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="662f3-221">**Status**</span><span class="sxs-lookup"><span data-stu-id="662f3-221">**Status**</span></span>  
     <span data-ttu-id="662f3-222">Indica se a ação do assistente retornou como um todo o valor de **Êxito** ou de **Falha**.</span><span class="sxs-lookup"><span data-stu-id="662f3-222">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="662f3-223">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="662f3-223">**Message**</span></span>  
     <span data-ttu-id="662f3-224">Fornece qualquer mensagem de aviso ou erro retornada pelo processo.</span><span class="sxs-lookup"><span data-stu-id="662f3-224">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="662f3-225">**Report**</span><span class="sxs-lookup"><span data-stu-id="662f3-225">**Report**</span></span>  
     <span data-ttu-id="662f3-226">Cria um relatório contendo os resultados do Assistente para Criar Partição.</span><span class="sxs-lookup"><span data-stu-id="662f3-226">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="662f3-227">As opções são **Exibir Relatório**, **Salvar Relatório no Arquivo**, **Copiar Relatório na Área de Transferência**e **Enviar Relatório como Email**.</span><span class="sxs-lookup"><span data-stu-id="662f3-227">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="662f3-228">**Exibir Relatório**</span><span class="sxs-lookup"><span data-stu-id="662f3-228">**View Report**</span></span>  
     <span data-ttu-id="662f3-229">Abre a caixa de diálogo **Exibir Relatório** , que contém um relatório de texto do progresso do Assistente para Criar Partições.</span><span class="sxs-lookup"><span data-stu-id="662f3-229">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="662f3-230">**Salvar Relatório no Arquivo**</span><span class="sxs-lookup"><span data-stu-id="662f3-230">**Save Report to File**</span></span>  
     <span data-ttu-id="662f3-231">Abre a caixa de diálogo **Salvar Relatório Como** .</span><span class="sxs-lookup"><span data-stu-id="662f3-231">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="662f3-232">**Copiar Relatório na Área de Transferência**</span><span class="sxs-lookup"><span data-stu-id="662f3-232">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="662f3-233">Copia os resultados do relatório de progresso do assistente na Área de transferência.</span><span class="sxs-lookup"><span data-stu-id="662f3-233">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="662f3-234">**Enviar Relatório como Email**</span><span class="sxs-lookup"><span data-stu-id="662f3-234">**Send Report as Email**</span></span>  
     <span data-ttu-id="662f3-235">Copia os resultados do relatório de progresso do assistente para uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="662f3-235">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="662f3-236">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="662f3-236">When complete, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="662f3-237">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="662f3-237">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-compression-on-a-table"></a><span data-ttu-id="662f3-238">Para desabilitar a compactação em uma tabela</span><span class="sxs-lookup"><span data-stu-id="662f3-238">To disable compression on a table</span></span>  
  
1.  <span data-ttu-id="662f3-239">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="662f3-239">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="662f3-240">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="662f3-240">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="662f3-241">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="662f3-241">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Person.Person REBUILD PARTITION = ALL  
    WITH (DATA_COMPRESSION = NONE);  
    GO  
    ```  
  
#### <a name="to-disable-compression-on-an-index"></a><span data-ttu-id="662f3-242">Para desabilitar a compactação em um índice</span><span class="sxs-lookup"><span data-stu-id="662f3-242">To disable compression on an index</span></span>  
  
1.  <span data-ttu-id="662f3-243">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="662f3-243">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="662f3-244">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="662f3-244">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="662f3-245">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="662f3-245">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER INDEX AK_Person_rowguid ON Person.Person REBUILD PARTITION = ALL WITH (DATA_COMPRESSION = NONE);  
    GO  
    ```  
  
 <span data-ttu-id="662f3-246">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) e [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="662f3-246">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
