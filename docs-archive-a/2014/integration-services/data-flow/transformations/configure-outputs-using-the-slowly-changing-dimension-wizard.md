---
title: Configurar saídas por meio do Assistente para Dimensões de Alteração Lenta | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Slowly Changing Dimension transformation
- slowly changing dimensions
- Slowly Changing Dimension Wizard
ms.assetid: da111731-1ffa-49b9-bcaa-3c93fd0eb619
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6ec3dfb34de8eb7e20b255ce485ee506f070749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575247"
---
# <a name="configure-outputs-using-the-slowly-changing-dimension-wizard"></a><span data-ttu-id="40d89-102">Configurar saídas por meio do Assistente para Dimensões de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="40d89-102">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>
  <span data-ttu-id="40d89-103">O Assistente para Dimensões de Alteração Lenta funciona como o editor da transformação Dimensão de Alteração Lenta.</span><span class="sxs-lookup"><span data-stu-id="40d89-103">The Slowly Changing Dimension Wizard functions as the editor for the Slowly Changing Dimension transformation.</span></span> <span data-ttu-id="40d89-104">Criar e configurar o fluxo de dados para alterar dados de dimensão lentamente pode ser uma tarefa complexa.</span><span class="sxs-lookup"><span data-stu-id="40d89-104">Building and configuring the data flow for slowly changing dimension data can be a complex task.</span></span> <span data-ttu-id="40d89-105">O Assistente para Dimensões de Alteração Lenta oferece o método mais simples para criar o fluxo de dados para as saídas da transformação Dimensão de Alteração Lenta, guiando você pelas etapas de mapeamento de colunas, selecionando colunas de chave de negócio, definindo atributos de alteração de coluna e configurando o suporte para membros de dimensão deduzidos.</span><span class="sxs-lookup"><span data-stu-id="40d89-105">The Slowly Changing Dimension Wizard offers the simplest method of building the data flow for the Slowly Changing Dimension transformation outputs by guiding you through the steps of mapping columns, selecting business key columns, setting column change attributes, and configuring support for inferred dimension members.</span></span>

 <span data-ttu-id="40d89-106">Você deve escolher pelo menos uma coluna de chave de negócio na tabela de dimensões e mapeá-la para uma coluna de entrada.</span><span class="sxs-lookup"><span data-stu-id="40d89-106">You must choose at least one business key column in the dimension table and map it to an input column.</span></span> <span data-ttu-id="40d89-107">O valor da chave de negócio vincula um registro na fonte a um registro na tabela de dimensões.</span><span class="sxs-lookup"><span data-stu-id="40d89-107">The value of the business key links a record in the source to a record in the dimension table.</span></span> <span data-ttu-id="40d89-108">A transformação usa esse mapeamento para localizar o registro na tabela de dimensões e determinar se um registro é novo ou está em alteração.</span><span class="sxs-lookup"><span data-stu-id="40d89-108">The transformation uses this mapping to locate the record in the dimension table and to determine whether a record is new or changing.</span></span> <span data-ttu-id="40d89-109">A chave de negócio é geralmente a chave primária na fonte, mas poderá ser uma chave alternativa desde que identifique um registro com exclusividade e seu valor não se altere.</span><span class="sxs-lookup"><span data-stu-id="40d89-109">The business key is typically the primary key in the source, but it can be an alternate key as long as it uniquely identifies a record and its value does not change.</span></span> <span data-ttu-id="40d89-110">A chave de negócio também pode ser uma chave composta, que consiste em várias colunas.</span><span class="sxs-lookup"><span data-stu-id="40d89-110">The business key can also be a composite key, consisting of multiple columns.</span></span> <span data-ttu-id="40d89-111">A chave primária na tabela de dimensões é geralmente uma chave substituta, o que significa um valor numérico gerado automaticamente por uma coluna de identidade ou por uma solução personalizada, como um script.</span><span class="sxs-lookup"><span data-stu-id="40d89-111">The primary key in the dimension table is usually a surrogate key, which means a numeric value generated automatically by an identity column or by a custom solution such as a script.</span></span>

 <span data-ttu-id="40d89-112">Antes de poder executar o Assistente para Dimensões de Alteração Lenta, você deve adicionar uma fonte e uma transformação Dimensão de Alteração Lenta ao fluxo de dados e conectar a saída da fonte à entrada da transformação Dimensão de Alteração Lenta.</span><span class="sxs-lookup"><span data-stu-id="40d89-112">Before you can run the Slowly Changing Dimension Wizard, you must add a source and a Slowly Changing Dimension transformation to the data flow, and then connect the output from the source to the input of the Slowly Changing Dimension transformation.</span></span> <span data-ttu-id="40d89-113">Opcionalmente, o fluxo de dados pode incluir outras transformações entre a fonte de dados e a transformação Dimensão de Alteração Lenta.</span><span class="sxs-lookup"><span data-stu-id="40d89-113">Optionally, the data flow can include other transformations between the data source and the Slowly Changing Dimension transformation.</span></span>

 <span data-ttu-id="40d89-114">Para abrir o Assistente para Dimensões de Alteração Lenta no Designer [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , clique duas vezes na transformação Dimensão de Alteração Lenta.</span><span class="sxs-lookup"><span data-stu-id="40d89-114">To open the Slowly Changing Dimension Wizard in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, double-click the Slowly Changing Dimension transformation.</span></span>

## <a name="creating-slowly-changing-dimension-outputs"></a><span data-ttu-id="40d89-115">Criando saídas de Dimensão de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="40d89-115">Creating Slowly Changing Dimension Outputs</span></span>

#### <a name="to-create-slowly-changing-dimension-transformation-outputs"></a><span data-ttu-id="40d89-116">Para criar saídas da transformação Dimensão de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="40d89-116">To create Slowly Changing Dimension transformation outputs</span></span>

1.  <span data-ttu-id="40d89-117">Escolha o gerenciador de conexões para acessar a fonte de dados que contém a tabela de dimensões que você quer atualizar.</span><span class="sxs-lookup"><span data-stu-id="40d89-117">Choose the connection manager to access the data source that contains the dimension table that you want to update.</span></span>

     <span data-ttu-id="40d89-118">Você pode selecionar em uma lista de gerenciadores de conexões incluídos no pacote.</span><span class="sxs-lookup"><span data-stu-id="40d89-118">You can select from a list of connection managers that the package includes.</span></span>

2.  <span data-ttu-id="40d89-119">Escolha a tabela de dimensões ou exibição que você quer atualizar.</span><span class="sxs-lookup"><span data-stu-id="40d89-119">Choose the dimension table or view you want to update.</span></span>

     <span data-ttu-id="40d89-120">Depois de selecionar o gerenciador de conexões, você pode selecionar a tabela ou a exibição na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="40d89-120">After you select the connection manager, you can select the table or view from the data source.</span></span>

3.  <span data-ttu-id="40d89-121">Defina atributos de chave em colunas e mapeie colunas de entrada para colunas na tabela de dimensões.</span><span class="sxs-lookup"><span data-stu-id="40d89-121">Set key attributes on columns and map input columns to columns in the dimension table.</span></span>

     <span data-ttu-id="40d89-122">Você deve escolher pelo menos uma coluna de chave de negócio na tabela de dimensões e mapeá-la para uma coluna de entrada.</span><span class="sxs-lookup"><span data-stu-id="40d89-122">You must choose at least one business key column in the dimension table and map it to an input column.</span></span> <span data-ttu-id="40d89-123">Outras colunas de entrada podem ser mapeadas para colunas na tabela de dimensões como mapeamentos não chave.</span><span class="sxs-lookup"><span data-stu-id="40d89-123">Other input columns can be mapped to columns in the dimension table as non-key mappings.</span></span>

4.  <span data-ttu-id="40d89-124">Escolha o tipo de alteração para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="40d89-124">Choose the change type for each column.</span></span>

    -   <span data-ttu-id="40d89-125">O**Atributo de alteração** substitui valores existentes em registros.</span><span class="sxs-lookup"><span data-stu-id="40d89-125">**Changing attribute** overwrites existing values in records.</span></span>

    -   <span data-ttu-id="40d89-126">O**Atributo histórico** cria registros novos em vez de atualizar registros existentes.</span><span class="sxs-lookup"><span data-stu-id="40d89-126">**Historical attribute** creates new records instead of updating existing records.</span></span>

    -   <span data-ttu-id="40d89-127">O**Atributo fixo** indica que o valor da coluna não deve ser alterado.</span><span class="sxs-lookup"><span data-stu-id="40d89-127">**Fixed attribute** indicates that the column value must not change.</span></span>

5.  <span data-ttu-id="40d89-128">Defina opções de atributo fixo e de alteração.</span><span class="sxs-lookup"><span data-stu-id="40d89-128">Set fixed and changing attribute options.</span></span>

     <span data-ttu-id="40d89-129">Se você configurar colunas para usar o tipo de alteração **Atributo fixo** , poderá especificar se a transformação Dimensão de Alteração Lenta sofrerá falha quando forem detectadas alterações nessas colunas.</span><span class="sxs-lookup"><span data-stu-id="40d89-129">If you configure columns to use the **Fixed attribute** change type, you can specify whether the Slowly Changing Dimension transformation fails when changes are detected in these columns.</span></span> <span data-ttu-id="40d89-130">Se você configurar colunas para usar o tipo de alteração **Atributo de alteração** , poderá especificar se todos os registros correspondentes, inclusive os registros desatualizados, serão atualizados.</span><span class="sxs-lookup"><span data-stu-id="40d89-130">If you configure columns to use the **Changing attribute** change type, you can specify whether all matching records, including outdated records, are updated.</span></span>

6.  <span data-ttu-id="40d89-131">Defina opções de atributo histórico.</span><span class="sxs-lookup"><span data-stu-id="40d89-131">Set historical attribute options.</span></span>

     <span data-ttu-id="40d89-132">Se você configurar colunas para usar o tipo de alteração **Atributo histórico** , deverá escolher como distinguir entre registros atuais e expirados.</span><span class="sxs-lookup"><span data-stu-id="40d89-132">If you configure columns to use the **Historical attribute** change type, you must choose how to distinguish between current and expired records.</span></span> <span data-ttu-id="40d89-133">Você pode usar uma coluna de indicador de linha atual ou duas colunas de data para identificar linhas atuais e expiradas.</span><span class="sxs-lookup"><span data-stu-id="40d89-133">You can use a current row indicator column or two date columns to identify current and expired rows.</span></span> <span data-ttu-id="40d89-134">Se você usar uma coluna de indicador de linha atual, poderá defini-la como **Atual**, **Verdadeira** quando atual e **Expirada** ou **Falsa** quando expirada.</span><span class="sxs-lookup"><span data-stu-id="40d89-134">If you use the current row indicator column, you can set it to **Current**, **True** when current and **Expired,** or **False** when expired.</span></span> <span data-ttu-id="40d89-135">Você também pode inserir valores personalizados.</span><span class="sxs-lookup"><span data-stu-id="40d89-135">You can also enter custom values.</span></span> <span data-ttu-id="40d89-136">Se usar duas colunas de data, uma data inicial e uma final, você poderá especificar a data que será usada quando os valores da coluna de data forem definidos digitando uma data ou selecionando uma variável de sistema e depois usando seu valor.</span><span class="sxs-lookup"><span data-stu-id="40d89-136">If you use two date columns, a start date and an end date, you can specify the date to use when setting the date column values by typing a date or by selecting a system variable and then using its value.</span></span>

7.  <span data-ttu-id="40d89-137">Especifique o suporte para membros deduzidos e escolha as colunas que o registro de membro deduzido contém.</span><span class="sxs-lookup"><span data-stu-id="40d89-137">Specify support for inferred members and choose the columns that the inferred member record contains.</span></span>

     <span data-ttu-id="40d89-138">Quando estiver carregando medidas em uma tabela de fatos, você poderá criar registros mínimos para membros deduzidos que ainda não existem.</span><span class="sxs-lookup"><span data-stu-id="40d89-138">When loading measures into a fact table, you can create minimal records for inferred members that do not yet exist.</span></span> <span data-ttu-id="40d89-139">Posteriormente, quando dados significantes estiverem disponíveis, os registros de dimensão poderão ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="40d89-139">Later, when meaningful data is available, the dimension records can be updated.</span></span> <span data-ttu-id="40d89-140">Podem ser criados os seguintes tipos de registros mínimos:</span><span class="sxs-lookup"><span data-stu-id="40d89-140">The following types of minimal records can be created:</span></span>

    -   <span data-ttu-id="40d89-141">Um registro no qual todas as colunas com tipos de alteração são nulas.</span><span class="sxs-lookup"><span data-stu-id="40d89-141">A record in which all columns with change types are null.</span></span>

    -   <span data-ttu-id="40d89-142">Um registro no qual uma coluna Booleana indica que o registro é um membro deduzido.</span><span class="sxs-lookup"><span data-stu-id="40d89-142">A record in which a Boolean column indicates the record is an inferred member.</span></span>

8.  <span data-ttu-id="40d89-143">Verifique as configurações que o Assistente para Dimensões de Alteração Lenta cria.</span><span class="sxs-lookup"><span data-stu-id="40d89-143">Review the configurations that the Slowly Changing Dimension Wizard builds.</span></span> <span data-ttu-id="40d89-144">Dependendo de quais tipos de alteração tiverem suporte, diferentes conjuntos de componentes de fluxo de dados serão adicionados ao pacote.</span><span class="sxs-lookup"><span data-stu-id="40d89-144">Depending on which change types are supported, different sets of data flow components are added to the package.</span></span>

     <span data-ttu-id="40d89-145">O diagrama a seguir exibe um exemplo de fluxo de dados que oferece suporte a atributos fixos, atributos de alteração e alterações de atributo histórico, membros deduzidos e alterações de registros correspondentes.</span><span class="sxs-lookup"><span data-stu-id="40d89-145">The following diagram shows an example of a data flow that supports fixed attribute, changing attribute, and historical attribute changes, inferred members, and changes to matching records.</span></span>

     <span data-ttu-id="40d89-146">![Fluxo de dados do Assistente para Dimensões de Alteração Lenta](../../media/dimensionwizard.gif "Fluxo de dados do Assistente para Dimensões de Alteração Lenta")</span><span class="sxs-lookup"><span data-stu-id="40d89-146">![Data flow from Slowly Changing Dimension Wizard](../../media/dimensionwizard.gif "Data flow from Slowly Changing Dimension Wizard")</span></span>

## <a name="updating-slowly-changing-dimension-outputs"></a><span data-ttu-id="40d89-147">Atualizando saídas de Dimensão de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="40d89-147">Updating Slowly Changing Dimension Outputs</span></span>
 <span data-ttu-id="40d89-148">O modo mais simples de atualizar a configuração de saídas da transformação Dimensão de Alteração Lenta é executar novamente o Assistente para Dimensões de Alteração Lenta e modificar as propriedades das páginas do assistente.</span><span class="sxs-lookup"><span data-stu-id="40d89-148">The simplest way to update the configuration of the Slowly Changing Dimension transformation outputs is to rerun the Slowly Changing Dimension Wizard and modify properties from the wizard pages.</span></span> <span data-ttu-id="40d89-149">Você também pode atualizar a transformação Dimensão de Alteração Lenta usando a caixa de diálogo **Editor Avançado** ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="40d89-149">You can also update the Slowly Changing Dimension transformation using the **Advanced Editor** dialog box or programmatically.</span></span>

## <a name="see-also"></a><span data-ttu-id="40d89-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="40d89-150">See Also</span></span>
 [<span data-ttu-id="40d89-151">Transformação Dimensão de Alteração Lenta</span><span class="sxs-lookup"><span data-stu-id="40d89-151">Slowly Changing Dimension Transformation</span></span>](slowly-changing-dimension-transformation.md)

