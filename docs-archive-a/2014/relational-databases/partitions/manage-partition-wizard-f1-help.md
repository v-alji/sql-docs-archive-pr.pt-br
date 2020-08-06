---
title: Ajuda F1 do Assistente para Gerenciar Partição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.managepartition.getstart.f1
- sql12.swb.managepartition.selectoutput.f1
- sql12.swb.managepartition.partitionaction.f1
- sql12.swb.managepartition.switchout.f1
- sql12.swb.managepartition.summary.f1
- sql12.swb.managepartition.createjob.f1
- sql12.swb.managepartition.stagingtable.f1
- sql12.swb.managepartition.progress.f1
- sql12.swb.managepartition.switchin.f1
- sql12.swb.managepartition.selectswitchtables.f1
helpviewer_keywords:
- wizards [SQL Server Management Studio] See Manage Partition Wizard
ms.assetid: e2478d26-dea4-428d-98c5-aad2d2a30da8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 09b3e774168e9a48a0a387c3474b29f96081d875
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679328"
---
# <a name="manage-partition-wizard-f1-help"></a><span data-ttu-id="2d62e-102">Ajuda de F1 do Assistente para Gerenciar Partição</span><span class="sxs-lookup"><span data-stu-id="2d62e-102">Manage Partition Wizard F1 Help</span></span>
  <span data-ttu-id="2d62e-103">Use o **Assistente para Gerenciar Partição** para gerenciar e modificar as tabelas particionadas existentes por meio da troca de partição ou pela implementação de um cenário de janela deslizante.</span><span class="sxs-lookup"><span data-stu-id="2d62e-103">Use the **Manage Partition Wizard** to manage and modify existing partitioned tables through partition switching or the implementation of a sliding window scenario.</span></span> <span data-ttu-id="2d62e-104">Esse assistente pode facilitar o gerenciamento das partições e simplificar a migração regular de dados de e para as tabelas.</span><span class="sxs-lookup"><span data-stu-id="2d62e-104">This wizard can ease the management of your partitions and simplify the regular migration of data in and out of your tables.</span></span>  
  
### <a name="to-start-the-manage-partition-wizard"></a><span data-ttu-id="2d62e-105">Para iniciar o Assistente para Gerenciar Partição</span><span class="sxs-lookup"><span data-stu-id="2d62e-105">To start the Manage Partition Wizard</span></span>  
  
-   <span data-ttu-id="2d62e-106">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], selecione o banco de dados, clique com o botão direito do mouse na tabela em que você deseja criar partições, aponte para **Armazenamento**e clique em **Gerenciar Partição**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the database, right-click the table on which you want to create partitions, point to **Storage**, and then click **Manage Partition**.</span></span>  
  
     <span data-ttu-id="2d62e-107">`Note`Se a **partição de gerenciamento** não estiver disponível, você poderá ter selecionado uma tabela que não contém partições.</span><span class="sxs-lookup"><span data-stu-id="2d62e-107">`Note` If **Manage Partition** is unavailable, you may have selected a table that does not contain partitions.</span></span> <span data-ttu-id="2d62e-108">Clique em **Criar Partição** no submenu **Armazenamento** e use o **Assistente para Criar Partição** para criar partições na tabela.</span><span class="sxs-lookup"><span data-stu-id="2d62e-108">Click **Create Partition** on the **Storage** submenu and use the **Create Partition Wizard** to create partitions in your table.</span></span>  
  
 <span data-ttu-id="2d62e-109">Para obter mais informações sobre índices particionados, veja [Tabelas e índices particionados](partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="2d62e-109">For general information about partitions and indexes, see [Partitioned Tables and Indexes](partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="2d62e-110">Esta seção fornece as informações necessárias para gerenciar, modificar e implementar partições usando o **Assistente para Gerenciar Partição**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-110">This section provides the information that is required to manage, modify, and implement partitions using the **Manage Partition Wizard**.</span></span>  
  
##  <a name="in-this-section"></a><a name="Top"></a> <span data-ttu-id="2d62e-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2d62e-111">In This Section</span></span>  
 <span data-ttu-id="2d62e-112">As seções a seguir fornecem ajuda sobre as páginas do **Assistente para Gerenciar Partição**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-112">The following sections provide help on the pages of the **Manage Partition Wizard**.</span></span>  
  
 [<span data-ttu-id="2d62e-113">Assistente para Gerenciar Partição (página Selecionar Ação de Partição)</span><span class="sxs-lookup"><span data-stu-id="2d62e-113">Manage Partition Wizard (Select Partition Action Page)</span></span>](#SelectPartitionAction)  
  
 [<span data-ttu-id="2d62e-114">Assistente para Gerenciar Partição (página de ativação)</span><span class="sxs-lookup"><span data-stu-id="2d62e-114">Manage Partition Wizard (Switch In Page)</span></span>](#SwitchIn)  
  
 [<span data-ttu-id="2d62e-115">Assistente para Gerenciar Partição (página de desativação)</span><span class="sxs-lookup"><span data-stu-id="2d62e-115">Manage Partition Wizard (Switch Out Page)</span></span>](#SwitchOut)  
  
 [<span data-ttu-id="2d62e-116">Assistente para Gerenciar Partição (Página Selecionar Opções da Tabela de Preparação)</span><span class="sxs-lookup"><span data-stu-id="2d62e-116">Manage Partition Wizard (Select Staging Table Options Page)</span></span>](#StagingTableOptions)  
  
 [<span data-ttu-id="2d62e-117">Assistente para Gerenciar Partição (página Selecionar Opção de Saída)</span><span class="sxs-lookup"><span data-stu-id="2d62e-117">Manage Partition Wizard (Select Output Option Page)</span></span>](#OutputOption)  
  
 [<span data-ttu-id="2d62e-118">Assistente para Gerenciar Partição (página Nova Agenda de Trabalho)</span><span class="sxs-lookup"><span data-stu-id="2d62e-118">Manage Partition Wizard (New Job Schedule Page)</span></span>](#NewJob)  
  
 [<span data-ttu-id="2d62e-119">Assistente para Gerenciar Partição (página Resumo)</span><span class="sxs-lookup"><span data-stu-id="2d62e-119">Manage Partition Wizard (Summary Page)</span></span>](#Summary)  
  
 [<span data-ttu-id="2d62e-120">Assistente para Gerenciar Partição (página Progresso)</span><span class="sxs-lookup"><span data-stu-id="2d62e-120">Manage Partition Wizard (Progress Page)</span></span>](#Progress)  
  
##  <a name="select-partition-action-page"></a><a name="SelectPartitionAction"></a> <span data-ttu-id="2d62e-121">Página Selecionar Ação de Partição</span><span class="sxs-lookup"><span data-stu-id="2d62e-121">Select Partition Action Page</span></span>  
 <span data-ttu-id="2d62e-122">Use a página **Selecionar Ação de Partição** para escolher a ação que você deseja executar na partição.</span><span class="sxs-lookup"><span data-stu-id="2d62e-122">Use the **Select Partition Action** page to choose the action you want to perform on your partition.</span></span>  
  
### <a name="create-a-staging-table"></a><span data-ttu-id="2d62e-123">Criar uma tabela de preparação</span><span class="sxs-lookup"><span data-stu-id="2d62e-123">Create a Staging Table</span></span>  
 <span data-ttu-id="2d62e-124">A alternação de partições é uma tarefa de particionamento comum se houver uma tabela particionada para a qual e da qual você migrou dados com certa regularidade; por exemplo, existe uma tabela particionada que armazena dados trimestrais e você precisa mover novos dados para ela e arquivar dados antigos ao final de cada trimestre.</span><span class="sxs-lookup"><span data-stu-id="2d62e-124">Partition switching is a common partitioning task if you have a partitioned table that you migrate data into and out of on a regular basis; for example, you have a partitioned table that stores current quarterly data, and you must move in new data and archive older data at the end of each quarter.</span></span>  
  
 <span data-ttu-id="2d62e-125">O assistente cria a tabela de preparação com a mesma estrutura de coluna de particionamento, tabela e coluna e com os mesmos índices e armazena a nova tabela no grupo de arquivos onde está a partição de origem.</span><span class="sxs-lookup"><span data-stu-id="2d62e-125">The wizard designs the staging table with the same partitioning column, table and column structure, and indexes, and stores the new table in the filegroup where your source partition is located.</span></span>  
  
 <span data-ttu-id="2d62e-126">Para criar uma tabela de preparo para inserir ou extrair os dados da partição, selecione **Criar uma tabela de preparo para alternar partições**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-126">To create a staging table to switch in or switch out partition data, select **Create a staging table for partition switching**.</span></span>  
  
### <a name="sliding-window-scenario"></a><span data-ttu-id="2d62e-127">Cenário de janela deslizante</span><span class="sxs-lookup"><span data-stu-id="2d62e-127">Sliding Window Scenario</span></span>  
 <span data-ttu-id="2d62e-128">Para gerenciar as partições em um cenário da janela deslizante, selecione **Gerenciar dados particionados em um cenário de janela deslizante**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-128">To manage your partitions in a sliding-window scenario, select **Manage partitioned data in a sliding window scenario**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2d62e-129">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="2d62e-129">UI element list</span></span>  
 <span data-ttu-id="2d62e-130">**Criar uma tabela de preparo para alternar partições**</span><span class="sxs-lookup"><span data-stu-id="2d62e-130">**Create a staging table for partition switching**</span></span>  
 <span data-ttu-id="2d62e-131">Cria uma tabela de preparação para os dados que você está ativando ou desativando na tabela particionada existente.</span><span class="sxs-lookup"><span data-stu-id="2d62e-131">Creates a staging table for the data you are switching in or switching out of the existing partitioned table.</span></span>  
  
 <span data-ttu-id="2d62e-132">**Desativar partição**</span><span class="sxs-lookup"><span data-stu-id="2d62e-132">**Switch out partition**</span></span>  
 <span data-ttu-id="2d62e-133">Fornece opções ao remover uma partição da tabela.</span><span class="sxs-lookup"><span data-stu-id="2d62e-133">Provides options when removing a partition from the table.</span></span>  
  
 <span data-ttu-id="2d62e-134">**Ativar partição**</span><span class="sxs-lookup"><span data-stu-id="2d62e-134">**Switch in partition**</span></span>  
 <span data-ttu-id="2d62e-135">Fornece opções ao adicionar uma partição à tabela.</span><span class="sxs-lookup"><span data-stu-id="2d62e-135">Provides options when adding a partition to the table.</span></span>  
  
 <span data-ttu-id="2d62e-136">**Gerenciar dados particionados em um cenário de janela deslizante**</span><span class="sxs-lookup"><span data-stu-id="2d62e-136">**Manage partitioned data in a sliding window scenario**</span></span>  
 <span data-ttu-id="2d62e-137">Acrescenta uma partição vazia à tabela existente que pode ser usada para alternar dados.</span><span class="sxs-lookup"><span data-stu-id="2d62e-137">Appends an empty partition to the existing table that can be used for switching in data.</span></span> <span data-ttu-id="2d62e-138">O assistente oferece suporte à alternância para a última partição e da primeira partição.</span><span class="sxs-lookup"><span data-stu-id="2d62e-138">The wizard currently supports switching into the last partition and switching out the first partition.</span></span>  
  
 <span data-ttu-id="2d62e-139">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Nesta seção](#Top)</span><span class="sxs-lookup"><span data-stu-id="2d62e-139">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-in-options-page"></a><a name="SwitchIn"></a> <span data-ttu-id="2d62e-140">Página Selecione as Opções de Inserção de Partição</span><span class="sxs-lookup"><span data-stu-id="2d62e-140">Select Partition Switching-In Options Page</span></span>  
 <span data-ttu-id="2d62e-141">Use a página **Selecione as opções de Inserção de Partição** para selecionar a tabela de preparo que você está ativando na tabela particionada.</span><span class="sxs-lookup"><span data-stu-id="2d62e-141">Use the **Select Partition Switching-In options** page to select the staging table you are switching into the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2d62e-142">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="2d62e-142">UI element list</span></span>  
 <span data-ttu-id="2d62e-143">**Mostrar Todas as Partições**</span><span class="sxs-lookup"><span data-stu-id="2d62e-143">**Show All Partitions**</span></span>  
 <span data-ttu-id="2d62e-144">Selecione para mostrar todas as partições, inclusive as partições que estão na tabela particionada no momento.</span><span class="sxs-lookup"><span data-stu-id="2d62e-144">Select to show all partitions, including the partitions currently in the partitioned table.</span></span>  
  
 <span data-ttu-id="2d62e-145">**Grade de partição**</span><span class="sxs-lookup"><span data-stu-id="2d62e-145">**Partition grid**</span></span>  
 <span data-ttu-id="2d62e-146">Exibe o nome da partição, o **Limite esquerdo**, o **Limite direito**, o **Grupo de arquivos**e a **Contagem de linhas** das partições selecionadas.</span><span class="sxs-lookup"><span data-stu-id="2d62e-146">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="2d62e-147">**Tabela de inserção**</span><span class="sxs-lookup"><span data-stu-id="2d62e-147">**Switch in table**</span></span>  
 <span data-ttu-id="2d62e-148">Selecione a partição de preparação que contém a partição à qual você deseja adicionar a tabela particionada.</span><span class="sxs-lookup"><span data-stu-id="2d62e-148">Select the staging table that contains the partition that you want to add to your partitioned table.</span></span> <span data-ttu-id="2d62e-149">É necessário criar essa tabela de preparo antes de ativar as partições com o **Assistente para Gerenciar Partições**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-149">You must create this staging table before you switch-in partitions with the **Manage PartitionsWizard**.</span></span>  
  
 <span data-ttu-id="2d62e-150">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Nesta seção](#Top)</span><span class="sxs-lookup"><span data-stu-id="2d62e-150">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-out-options-page"></a><a name="SwitchOut"></a> <span data-ttu-id="2d62e-151">Página Selecione as Opções de Extração de Partição</span><span class="sxs-lookup"><span data-stu-id="2d62e-151">Select Partition Switching-Out Options Page</span></span>  
 <span data-ttu-id="2d62e-152">Use a página **Selecione as opções de Extração de Partição** para selecionar a partição e a tabela de preparo para reter os dados particionados que você está desativando na tabela particionada.</span><span class="sxs-lookup"><span data-stu-id="2d62e-152">Use the **Select Partition Switching-Out options** page to select the partition and the staging table to hold the partitioned data that you are switching out of the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2d62e-153">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="2d62e-153">UI element list</span></span>  
 <span data-ttu-id="2d62e-154">**Grade de partição**</span><span class="sxs-lookup"><span data-stu-id="2d62e-154">**Partition grid**</span></span>  
 <span data-ttu-id="2d62e-155">Exibe o nome da partição, o **Limite esquerdo**, o **Limite direito**, o **Grupo de arquivos**e a **Contagem de linhas** das partições selecionadas.</span><span class="sxs-lookup"><span data-stu-id="2d62e-155">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="2d62e-156">**Tabela de extração**</span><span class="sxs-lookup"><span data-stu-id="2d62e-156">**Switch out table**</span></span>  
 <span data-ttu-id="2d62e-157">Escolha uma nova tabela ou uma tabela existente no qual os dados serão desativados.</span><span class="sxs-lookup"><span data-stu-id="2d62e-157">Choose a new table or an existing table to switch-out your data to.</span></span>  
  
 <span data-ttu-id="2d62e-158">**Novo**</span><span class="sxs-lookup"><span data-stu-id="2d62e-158">**New**</span></span>  
 <span data-ttu-id="2d62e-159">Digite um novo nome para a tabela de preparação que você deseja usar para a partição a ser desativada da tabela de origem atual.</span><span class="sxs-lookup"><span data-stu-id="2d62e-159">Enter a new name for the staging table you want to use for the partition to switch out of the current source table.</span></span>  
  
 <span data-ttu-id="2d62e-160">**Existente**</span><span class="sxs-lookup"><span data-stu-id="2d62e-160">**Existing**</span></span>  
 <span data-ttu-id="2d62e-161">Selecione uma tabela de preparação existente que você deseja usar para a partição a ser desativada da tabela de origem atual.</span><span class="sxs-lookup"><span data-stu-id="2d62e-161">Select an existing staging table you want to use for the partition you want to switch out of the current source table.</span></span> <span data-ttu-id="2d62e-162">Se a tabela existente contiver dados, eles serão substituídos pelos dados que você está desativando.</span><span class="sxs-lookup"><span data-stu-id="2d62e-162">If the existing table contains data, this data will be overwritten with the data you are switching out.</span></span>  
  
 <span data-ttu-id="2d62e-163">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Nesta seção](#Top)</span><span class="sxs-lookup"><span data-stu-id="2d62e-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-the-staging-table-options-page"></a><a name="StagingTableOptions"></a> <span data-ttu-id="2d62e-164">Página Selecionar Opções da Tabela de Preparação</span><span class="sxs-lookup"><span data-stu-id="2d62e-164">Select the Staging Table Options Page</span></span>  
 <span data-ttu-id="2d62e-165">Use a página **Selecionar Opções da Tabela de Preparação** para criar a tabela de preparo que você deseja usar para alternar os dados particionados.</span><span class="sxs-lookup"><span data-stu-id="2d62e-165">Use the **Select the Staging Table Options** page to create the staging table you want to use for switching your partitioned data.</span></span>  
  
 <span data-ttu-id="2d62e-166">As tabelas de preparação devem residir no mesmo grupo de arquivos da partição selecionada da tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="2d62e-166">Staging tables must reside in the same filegroup of the selected partition where the source table is located.</span></span> <span data-ttu-id="2d62e-167">A tabela de preparação deve espelhar o design da tabela de origem e da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="2d62e-167">The staging table must mirror the design of both the source table and the destination table.</span></span>  
  
 <span data-ttu-id="2d62e-168">Também é possível criar os mesmos índices na tabela de preparação existente na partição de origem.</span><span class="sxs-lookup"><span data-stu-id="2d62e-168">You can also create the same indexes in the staging table that exist in the source partition.</span></span> <span data-ttu-id="2d62e-169">A tabela de preparação contém automaticamente uma restrição que se baseia nos elementos da partição de origem.</span><span class="sxs-lookup"><span data-stu-id="2d62e-169">The staging table automatically contains a constraint based on the elements of the source partition.</span></span> <span data-ttu-id="2d62e-170">Normalmente, essa restrição é gerada a partir do valor de limite da partição de origem.</span><span class="sxs-lookup"><span data-stu-id="2d62e-170">This constraint is typically generated from the boundary value of the source partition.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2d62e-171">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="2d62e-171">UI element list</span></span>  
 <span data-ttu-id="2d62e-172">**Nome da tabela de preparação**</span><span class="sxs-lookup"><span data-stu-id="2d62e-172">**Staging table name**</span></span>  
 <span data-ttu-id="2d62e-173">Crie um nome para a tabela de preparação ou aceite o nome padrão exibido na caixa de edição.</span><span class="sxs-lookup"><span data-stu-id="2d62e-173">Create a name for the staging table or accept the default name displayed in the edit box.</span></span>  
  
 <span data-ttu-id="2d62e-174">**Alternar partição**</span><span class="sxs-lookup"><span data-stu-id="2d62e-174">**Switch partition**</span></span>  
 <span data-ttu-id="2d62e-175">Selecione a partição de origem que você quer alternar com a tabela atual.</span><span class="sxs-lookup"><span data-stu-id="2d62e-175">Select the source partition that you want to switch out of the current table.</span></span>  
  
 <span data-ttu-id="2d62e-176">**Novo valor de limite**</span><span class="sxs-lookup"><span data-stu-id="2d62e-176">**New boundary value**</span></span>  
 <span data-ttu-id="2d62e-177">Selecione ou digite o valor de limite desejado para a partição da tabela de preparação.</span><span class="sxs-lookup"><span data-stu-id="2d62e-177">Select or enter the boundary value you want for the partition in the staging table.</span></span>  
  
 <span data-ttu-id="2d62e-178">**Grupo de arquivos**</span><span class="sxs-lookup"><span data-stu-id="2d62e-178">**Filegroup**</span></span>  
 <span data-ttu-id="2d62e-179">Selecione um grupo de arquivos para a nova tabela.</span><span class="sxs-lookup"><span data-stu-id="2d62e-179">Select a filegroup for the new table.</span></span>  
  
 <span data-ttu-id="2d62e-180">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Nesta seção](#Top)</span><span class="sxs-lookup"><span data-stu-id="2d62e-180">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-output-option-page"></a><a name="OutputOption"></a> <span data-ttu-id="2d62e-181">Página Selecionar Opção de Saída</span><span class="sxs-lookup"><span data-stu-id="2d62e-181">Select Output Option Page</span></span>  
 <span data-ttu-id="2d62e-182">Use a página **Selecionar Opção de Saída** para especificar como deseja concluir as modificações em suas partições.</span><span class="sxs-lookup"><span data-stu-id="2d62e-182">Use the **Select Output Option** page to specify how you want to complete the modifications to your partitions.</span></span>  
  
### <a name="create-script"></a><span data-ttu-id="2d62e-183">Criar script</span><span class="sxs-lookup"><span data-stu-id="2d62e-183">Create Script</span></span>  
 <span data-ttu-id="2d62e-184">Quando o assistente é concluído, ele cria um script no Editor de Consultas para modificar partições na tabela.</span><span class="sxs-lookup"><span data-stu-id="2d62e-184">When the wizard finishes, it creates a script in Query Editor to modify partitions in the table.</span></span> <span data-ttu-id="2d62e-185">Selecione **Criar Script** se desejar examinar o script. Em seguida, execute o script manualmente.</span><span class="sxs-lookup"><span data-stu-id="2d62e-185">Select **Create Script** if you want to review the script, and then execute the script manually.</span></span>  
  
 <span data-ttu-id="2d62e-186">**Script para arquivo**</span><span class="sxs-lookup"><span data-stu-id="2d62e-186">**Script to file**</span></span>  
 <span data-ttu-id="2d62e-187">Gere o script em um arquivo .sql.</span><span class="sxs-lookup"><span data-stu-id="2d62e-187">Generate the script to a .sql file.</span></span> <span data-ttu-id="2d62e-188">Especifique **Unicode** ou **Texto ANSI**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-188">Specify either **Unicode** or **ANSI text**.</span></span> <span data-ttu-id="2d62e-189">Para especificar nome e localização para o arquivo, clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-189">To specify a name and location for the file, click **Browse**.</span></span>  
  
 <span data-ttu-id="2d62e-190">**Script para Área de Transferência**</span><span class="sxs-lookup"><span data-stu-id="2d62e-190">**Script to Clipboard**</span></span>  
 <span data-ttu-id="2d62e-191">Salve o script na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="2d62e-191">Save the script to the Clipboard.</span></span>  
  
 <span data-ttu-id="2d62e-192">**Script para Nova Janela de Consulta**</span><span class="sxs-lookup"><span data-stu-id="2d62e-192">**Script to New Query Window**</span></span>  
 <span data-ttu-id="2d62e-193">Gere o script para uma janela do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="2d62e-193">Generate the script to a Query Editor window.</span></span> <span data-ttu-id="2d62e-194">Se não houver uma janela de editor aberta, uma nova janela será aberta como destino para o script.</span><span class="sxs-lookup"><span data-stu-id="2d62e-194">If no editor window is open, a new editor window opens as the target for the script.</span></span>  
  
### <a name="run-immediately"></a><span data-ttu-id="2d62e-195">Executar imediatamente</span><span class="sxs-lookup"><span data-stu-id="2d62e-195">Run Immediately</span></span>  
 <span data-ttu-id="2d62e-196">**Run immediately**</span><span class="sxs-lookup"><span data-stu-id="2d62e-196">**Run immediately**</span></span>  
 <span data-ttu-id="2d62e-197">Faça com que o assistente conclua as modificações nas partições quando você clicar em **Avançar** ou em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-197">Have the wizard finish modifications to the partitions when you click **Next** or **Finish**.</span></span>  
  
### <a name="schedule"></a><span data-ttu-id="2d62e-198">Agenda</span><span class="sxs-lookup"><span data-stu-id="2d62e-198">Schedule</span></span>  
 <span data-ttu-id="2d62e-199">Selecione para modificar as partições de tabela na data e na hora agendadas.</span><span class="sxs-lookup"><span data-stu-id="2d62e-199">Select to modify the table partitions at a scheduled date and time.</span></span>  
  
 <span data-ttu-id="2d62e-200">**Alterar agenda**</span><span class="sxs-lookup"><span data-stu-id="2d62e-200">**Change schedule**</span></span>  
 <span data-ttu-id="2d62e-201">Abre a caixa de diálogo **Novo Agendamento de Trabalho** , em que é possível selecionar, alterar ou exibir as propriedades do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="2d62e-201">Opens the **New Job Schedule** dialog box, where you can select, change, or view the properties of the scheduled job.</span></span>  
  
 <span data-ttu-id="2d62e-202">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Nesta seção](#Top)</span><span class="sxs-lookup"><span data-stu-id="2d62e-202">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="new-job-schedule-page"></a><a name="NewJob"></a> <span data-ttu-id="2d62e-203">Página Nova Agenda de Trabalho</span><span class="sxs-lookup"><span data-stu-id="2d62e-203">New Job Schedule Page</span></span>  
 <span data-ttu-id="2d62e-204">Use a página **Novo Agendamento de Trabalho** para exibir e alterar as propriedades do agendamento.</span><span class="sxs-lookup"><span data-stu-id="2d62e-204">Use the **New Job Schedule** page to view and change the properties of the schedule.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2d62e-205">Opções</span><span class="sxs-lookup"><span data-stu-id="2d62e-205">Options</span></span>  
 <span data-ttu-id="2d62e-206">Selecione o tipo de agenda que deseja para o trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="2d62e-206">Select the type of schedule you want for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
 <span data-ttu-id="2d62e-207">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2d62e-207">**Name**</span></span>  
 <span data-ttu-id="2d62e-208">Digite um nome novo para a agenda.</span><span class="sxs-lookup"><span data-stu-id="2d62e-208">Type a new name for the schedule.</span></span>  
  
 <span data-ttu-id="2d62e-209">**Trabalhos na agenda**</span><span class="sxs-lookup"><span data-stu-id="2d62e-209">**Jobs in schedule**</span></span>  
 <span data-ttu-id="2d62e-210">Exiba os trabalhos existentes que usam a agenda.</span><span class="sxs-lookup"><span data-stu-id="2d62e-210">View the existing jobs that use the schedule.</span></span>  
  
 <span data-ttu-id="2d62e-211">**Tipo de agenda**</span><span class="sxs-lookup"><span data-stu-id="2d62e-211">**Schedule type**</span></span>  
 <span data-ttu-id="2d62e-212">Selecione o tipo de agenda.</span><span class="sxs-lookup"><span data-stu-id="2d62e-212">Select the type of schedule.</span></span>  
  
 <span data-ttu-id="2d62e-213">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="2d62e-213">**Enabled**</span></span>  
 <span data-ttu-id="2d62e-214">Habilite ou desabilite a agenda.</span><span class="sxs-lookup"><span data-stu-id="2d62e-214">Enable or disable the schedule.</span></span>  
  
### <a name="recurring-schedule-types-options"></a><span data-ttu-id="2d62e-215">Opções de tipos de agenda recorrentes</span><span class="sxs-lookup"><span data-stu-id="2d62e-215">Recurring Schedule Types Options</span></span>  
 <span data-ttu-id="2d62e-216">Selecione a frequência do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="2d62e-216">Select the frequency of the scheduled job.</span></span>  
  
 <span data-ttu-id="2d62e-217">**Ocorre**</span><span class="sxs-lookup"><span data-stu-id="2d62e-217">**Occurs**</span></span>  
 <span data-ttu-id="2d62e-218">Selecione o intervalo no qual a agenda ocorre periodicamente.</span><span class="sxs-lookup"><span data-stu-id="2d62e-218">Select the interval at which the schedule recurs.</span></span>  
  
 <span data-ttu-id="2d62e-219">**Repete-se a cada**</span><span class="sxs-lookup"><span data-stu-id="2d62e-219">**Recurs every**</span></span>  
 <span data-ttu-id="2d62e-220">Selecione o número de dias ou semanas entre ocorrências periódicas da agenda.</span><span class="sxs-lookup"><span data-stu-id="2d62e-220">Select the number of days or weeks between recurrences of the schedule.</span></span> <span data-ttu-id="2d62e-221">Essa opção não está disponível para agendas mensais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-221">This option is not available for monthly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-222">**Segunda-feira**</span><span class="sxs-lookup"><span data-stu-id="2d62e-222">**Monday**</span></span>  
 <span data-ttu-id="2d62e-223">Defina o trabalho para ocorrer em uma segunda-feira.</span><span class="sxs-lookup"><span data-stu-id="2d62e-223">Set the job to occur on a Monday.</span></span> <span data-ttu-id="2d62e-224">Disponível somente para agendamentos semanais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-224">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-225">**Terça-feira**</span><span class="sxs-lookup"><span data-stu-id="2d62e-225">**Tuesday**</span></span>  
 <span data-ttu-id="2d62e-226">Defina o trabalho para ocorrer em uma terça-feira.</span><span class="sxs-lookup"><span data-stu-id="2d62e-226">Set the job to occur on a Tuesday.</span></span> <span data-ttu-id="2d62e-227">Disponível somente para agendamentos semanais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-227">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-228">**Quarta-feira**</span><span class="sxs-lookup"><span data-stu-id="2d62e-228">**Wednesday**</span></span>  
 <span data-ttu-id="2d62e-229">Defina o trabalho para ocorrer em uma quarta-feira.</span><span class="sxs-lookup"><span data-stu-id="2d62e-229">Set the job to occur on a Wednesday.</span></span> <span data-ttu-id="2d62e-230">Disponível somente para agendamentos semanais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-230">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-231">**Quinta-feira**</span><span class="sxs-lookup"><span data-stu-id="2d62e-231">**Thursday**</span></span>  
 <span data-ttu-id="2d62e-232">Defina o trabalho para ocorrer em uma quinta-feira.</span><span class="sxs-lookup"><span data-stu-id="2d62e-232">Set the job to occur on a Thursday.</span></span> <span data-ttu-id="2d62e-233">Disponível somente para agendamentos semanais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-233">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-234">**Sexta-feira**</span><span class="sxs-lookup"><span data-stu-id="2d62e-234">**Friday**</span></span>  
 <span data-ttu-id="2d62e-235">Defina o trabalho para ocorrer em uma sexta-feira.</span><span class="sxs-lookup"><span data-stu-id="2d62e-235">Set the job to occur on a Friday.</span></span> <span data-ttu-id="2d62e-236">Disponível somente para agendamentos semanais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-236">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-237">**Sábado**</span><span class="sxs-lookup"><span data-stu-id="2d62e-237">**Saturday**</span></span>  
 <span data-ttu-id="2d62e-238">Defina o trabalho para ocorrer em um sábado.</span><span class="sxs-lookup"><span data-stu-id="2d62e-238">Set the job to occur on a Saturday.</span></span> <span data-ttu-id="2d62e-239">Disponível somente para agendamentos semanais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-239">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-240">**Domingo**</span><span class="sxs-lookup"><span data-stu-id="2d62e-240">**Sunday**</span></span>  
 <span data-ttu-id="2d62e-241">Defina o trabalho para ocorrer em um domingo.</span><span class="sxs-lookup"><span data-stu-id="2d62e-241">Set the job to occur on a Sunday.</span></span> <span data-ttu-id="2d62e-242">Disponível somente para agendamentos semanais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-242">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-243">**Day**</span><span class="sxs-lookup"><span data-stu-id="2d62e-243">**Day**</span></span>  
 <span data-ttu-id="2d62e-244">Selecione o dia do mês que a agenda ocorre.</span><span class="sxs-lookup"><span data-stu-id="2d62e-244">Select the day of the month the schedule occurs.</span></span> <span data-ttu-id="2d62e-245">Disponível somente para agendas mensais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-245">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-246">**de cada**</span><span class="sxs-lookup"><span data-stu-id="2d62e-246">**of every**</span></span>  
 <span data-ttu-id="2d62e-247">Selecione o número de meses entre ocorrências da agenda.</span><span class="sxs-lookup"><span data-stu-id="2d62e-247">Select the number of months between occurrences of the schedule.</span></span> <span data-ttu-id="2d62e-248">Disponível somente para agendas mensais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-248">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-249">**O**</span><span class="sxs-lookup"><span data-stu-id="2d62e-249">**The**</span></span>  
 <span data-ttu-id="2d62e-250">Especifique uma agenda durante um dia específico da semana em uma semana específica durante o mês.</span><span class="sxs-lookup"><span data-stu-id="2d62e-250">Specify a schedule for a specific day of the week on a specific week within the month.</span></span> <span data-ttu-id="2d62e-251">Disponível somente para agendas mensais.</span><span class="sxs-lookup"><span data-stu-id="2d62e-251">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="2d62e-252">**Ocorre uma vez em**</span><span class="sxs-lookup"><span data-stu-id="2d62e-252">**Occurs once at**</span></span>  
 <span data-ttu-id="2d62e-253">Defina a hora para que um trabalho ocorra diariamente.</span><span class="sxs-lookup"><span data-stu-id="2d62e-253">Set the time for a job to occur daily.</span></span>  
  
 <span data-ttu-id="2d62e-254">**Ocorre a cada**</span><span class="sxs-lookup"><span data-stu-id="2d62e-254">**Occurs every**</span></span>  
 <span data-ttu-id="2d62e-255">Defina o número de horas ou minutos entre ocorrências.</span><span class="sxs-lookup"><span data-stu-id="2d62e-255">Set the number of hours or minutes between occurrences.</span></span>  
  
 <span data-ttu-id="2d62e-256">**Data de início**</span><span class="sxs-lookup"><span data-stu-id="2d62e-256">**Start date**</span></span>  
 <span data-ttu-id="2d62e-257">Defina a data quando essa agenda ficará efetiva.</span><span class="sxs-lookup"><span data-stu-id="2d62e-257">Set the date when this schedule will become effective.</span></span>  
  
 <span data-ttu-id="2d62e-258">**Data de término**</span><span class="sxs-lookup"><span data-stu-id="2d62e-258">**End date**</span></span>  
 <span data-ttu-id="2d62e-259">Defina a data quando a agenda já não será válida.</span><span class="sxs-lookup"><span data-stu-id="2d62e-259">Set the date when the schedule will no longer be effective.</span></span>  
  
 <span data-ttu-id="2d62e-260">**Nenhuma data de término**</span><span class="sxs-lookup"><span data-stu-id="2d62e-260">**No end date**</span></span>  
 <span data-ttu-id="2d62e-261">Especifique que a agenda permanecerá efetiva indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="2d62e-261">Specify that the schedule will remain effective indefinitely.</span></span>  
  
### <a name="one-time-schedule-types-options"></a><span data-ttu-id="2d62e-262">Opções de tipos de agendas que ocorrem apenas uma vez</span><span class="sxs-lookup"><span data-stu-id="2d62e-262">One Time Schedule Types Options</span></span>  
 <span data-ttu-id="2d62e-263">Se você agendar um trabalho para uma única execução, selecione uma data e uma hora no futuro.</span><span class="sxs-lookup"><span data-stu-id="2d62e-263">If you schedule a job to run once, you must select a date and time in the future.</span></span>  
  
 <span data-ttu-id="2d62e-264">**Data**</span><span class="sxs-lookup"><span data-stu-id="2d62e-264">**Date**</span></span>  
 <span data-ttu-id="2d62e-265">Selecione a data para que o trabalho seja executado.</span><span class="sxs-lookup"><span data-stu-id="2d62e-265">Select the date for the job to run.</span></span>  
  
 <span data-ttu-id="2d62e-266">**Hora**</span><span class="sxs-lookup"><span data-stu-id="2d62e-266">**Time**</span></span>  
 <span data-ttu-id="2d62e-267">Selecione a hora para que o trabalho seja executado.</span><span class="sxs-lookup"><span data-stu-id="2d62e-267">Select the time for the job to run.</span></span>  
  
 <span data-ttu-id="2d62e-268">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Nesta seção](#Top)</span><span class="sxs-lookup"><span data-stu-id="2d62e-268">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="2d62e-269">Página de Resumo</span><span class="sxs-lookup"><span data-stu-id="2d62e-269">Summary Page</span></span>  
 <span data-ttu-id="2d62e-270">Use a página **Resumo** para examinar as opções selecionadas nas páginas anteriores.</span><span class="sxs-lookup"><span data-stu-id="2d62e-270">Use the **Summary** page to review the options that you have selected on the previous pages.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2d62e-271">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="2d62e-271">UI element list</span></span>  
 <span data-ttu-id="2d62e-272">**Examinar as seleções**</span><span class="sxs-lookup"><span data-stu-id="2d62e-272">**Review your selections**</span></span>  
 <span data-ttu-id="2d62e-273">Exibe as seleções feitas em cada página do assistente.</span><span class="sxs-lookup"><span data-stu-id="2d62e-273">Displays the selections you have made for each page of the wizard.</span></span> <span data-ttu-id="2d62e-274">Clique em um nó para expandir e exibir as opções selecionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2d62e-274">Click a node to expand and view your previously selected options.</span></span>  
  
 <span data-ttu-id="2d62e-275">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Nesta seção](#Top)</span><span class="sxs-lookup"><span data-stu-id="2d62e-275">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="2d62e-276">Página Progresso</span><span class="sxs-lookup"><span data-stu-id="2d62e-276">Progress Page</span></span>  
 <span data-ttu-id="2d62e-277">Use a página **Progresso** para monitorar informações de status das ações do **Assistente para Gerenciar Partição**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-277">Use the **Progress** page to monitor status information about the actions of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="2d62e-278">Dependendo das opções selecionadas no assistente, a página **Progresso** pode conter uma ou várias ações.</span><span class="sxs-lookup"><span data-stu-id="2d62e-278">Depending on the options that you selected in the wizard, the **Progress** page might contain one or more actions.</span></span> <span data-ttu-id="2d62e-279">A caixa superior exibe o status geral do assistente e o número de mensagens de status, erro e aviso que ele recebeu.</span><span class="sxs-lookup"><span data-stu-id="2d62e-279">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2d62e-280">Opções</span><span class="sxs-lookup"><span data-stu-id="2d62e-280">Options</span></span>  
 <span data-ttu-id="2d62e-281">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2d62e-281">**Details**</span></span>  
 <span data-ttu-id="2d62e-282">Fornece a ação, status e qualquer mensagem retornada pela ação executada pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="2d62e-282">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
 <span data-ttu-id="2d62e-283">**Ação**</span><span class="sxs-lookup"><span data-stu-id="2d62e-283">**Action**</span></span>  
 <span data-ttu-id="2d62e-284">Especifica o tipo e o nome de cada ação.</span><span class="sxs-lookup"><span data-stu-id="2d62e-284">Specifies the type and name of each action.</span></span>  
  
 <span data-ttu-id="2d62e-285">**Status**</span><span class="sxs-lookup"><span data-stu-id="2d62e-285">**Status**</span></span>  
 <span data-ttu-id="2d62e-286">Indica se a ação do assistente retornou como um todo o valor de **Êxito** ou de **Falha**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-286">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
 <span data-ttu-id="2d62e-287">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="2d62e-287">**Message**</span></span>  
 <span data-ttu-id="2d62e-288">Fornece qualquer mensagem de aviso ou erro retornada pelo processo.</span><span class="sxs-lookup"><span data-stu-id="2d62e-288">Provides any error or warning messages that are returned from the process.</span></span>  
  
 <span data-ttu-id="2d62e-289">**Parar**</span><span class="sxs-lookup"><span data-stu-id="2d62e-289">**Stop**</span></span>  
 <span data-ttu-id="2d62e-290">Interrompe a ação do assistente.</span><span class="sxs-lookup"><span data-stu-id="2d62e-290">Stop the action of the wizard.</span></span>  
  
 <span data-ttu-id="2d62e-291">**Report**</span><span class="sxs-lookup"><span data-stu-id="2d62e-291">**Report**</span></span>  
 <span data-ttu-id="2d62e-292">Crie um relatório contendo os resultados do **Assistente para Gerenciar Partição**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-292">Create a report that contains the results of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="2d62e-293">As opções são:</span><span class="sxs-lookup"><span data-stu-id="2d62e-293">The options are:</span></span>  
  
-   <span data-ttu-id="2d62e-294">**Exibir Relatório**</span><span class="sxs-lookup"><span data-stu-id="2d62e-294">**View Report**</span></span>  
  
-   <span data-ttu-id="2d62e-295">**Salvar Relatório no Arquivo**</span><span class="sxs-lookup"><span data-stu-id="2d62e-295">**Save Report to File**</span></span>  
  
-   <span data-ttu-id="2d62e-296">**Copiar Relatório na Área de Transferência**</span><span class="sxs-lookup"><span data-stu-id="2d62e-296">**Copy Report to Clipboard**</span></span>  
  
-   <span data-ttu-id="2d62e-297">**Enviar Relatório como Email**</span><span class="sxs-lookup"><span data-stu-id="2d62e-297">**Send Report as Email**</span></span>  
  
 <span data-ttu-id="2d62e-298">**Exibir Relatório**</span><span class="sxs-lookup"><span data-stu-id="2d62e-298">**View Report**</span></span>  
 <span data-ttu-id="2d62e-299">Abra a caixa de diálogo **Exibir Relatório** .</span><span class="sxs-lookup"><span data-stu-id="2d62e-299">Open the **View Report** dialog box.</span></span> <span data-ttu-id="2d62e-300">Essa caixa de diálogo contém um relatório de texto do progresso do **Assistente para Gerenciar Partição**.</span><span class="sxs-lookup"><span data-stu-id="2d62e-300">This dialog box contains a text report of the progress of the **Manage Partition Wizard**.</span></span>  
  
 <span data-ttu-id="2d62e-301">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="2d62e-301">**Close**</span></span>  
 <span data-ttu-id="2d62e-302">Feche o assistente.</span><span class="sxs-lookup"><span data-stu-id="2d62e-302">Close the wizard.</span></span>  
  
 <span data-ttu-id="2d62e-303">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Nesta seção](#Top)</span><span class="sxs-lookup"><span data-stu-id="2d62e-303">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d62e-304">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d62e-304">See Also</span></span>  
 [<span data-ttu-id="2d62e-305">Tabelas e índices particionados</span><span class="sxs-lookup"><span data-stu-id="2d62e-305">Partitioned Tables and Indexes</span></span>](partitioned-tables-and-indexes.md)  
  
  
