---
title: Criar e gerenciar KPIs (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.kpi.f1
ms.assetid: c96026c2-4394-4c3c-986b-4c95a4421900
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8e9d7ef77939efe407ed6ab0d725a6d788c58b49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572214"
---
# <a name="create-and-manage-kpis-ssas-tabular"></a><span data-ttu-id="02e12-102">Criar e Gerenciar KPIs (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="02e12-102">Create and Manage KPIs (SSAS Tabular)</span></span>
  <span data-ttu-id="02e12-103">Este tópico descreve como criar, editar ou excluir um KPI (Indicador chave de desempenho) em um modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="02e12-103">This topic describes how to create, edit, or delete a KPI (Key Performance Indicator) in a tabular model.</span></span> <span data-ttu-id="02e12-104">Para criar um KPI, você seleciona uma medida que é avaliada como o valor base do KPI.</span><span class="sxs-lookup"><span data-stu-id="02e12-104">To create a KPI, you select a measure that evaluates to the KPI's Base value.</span></span> <span data-ttu-id="02e12-105">Use a caixa de diálogo Indicador Chave de Desempenho para selecionar uma segunda medida ou um valor absoluto que seja avaliado para um valor de destino.</span><span class="sxs-lookup"><span data-stu-id="02e12-105">You then use the Key Performance Indicator dialog box to select a second measure or an absolute value that evaluates to a target value.</span></span> <span data-ttu-id="02e12-106">Em seguida, você pode definir os limites de status que abrangem o desempenho entre as medidas Base e Destino.</span><span class="sxs-lookup"><span data-stu-id="02e12-106">You can then define status thresholds that measure the performance between the Base and Target measures.</span></span>  
  
 <span data-ttu-id="02e12-107">Este tópico inclui as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="02e12-107">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="02e12-108">Para criar um KPI</span><span class="sxs-lookup"><span data-stu-id="02e12-108">To create a KPI</span></span>](#bkmk_create_KPI)  
  
-   [<span data-ttu-id="02e12-109">Para editar um KPI</span><span class="sxs-lookup"><span data-stu-id="02e12-109">To edit a KPI</span></span>](#bkmk_edit_KPI)  
  
-   [<span data-ttu-id="02e12-110">Para excluir um KPI e a medida base</span><span class="sxs-lookup"><span data-stu-id="02e12-110">To delete a KPI and the base measure</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="02e12-111">Para excluir um KPI, mas manter a medida de base</span><span class="sxs-lookup"><span data-stu-id="02e12-111">To delete a KPI, but keep the base measure</span></span>](#bkmk_delete_KPI)  
  
## <a name="tasks"></a><span data-ttu-id="02e12-112">Tarefas</span><span class="sxs-lookup"><span data-stu-id="02e12-112">Tasks</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="02e12-113">Antes de criar um KPI, primeiro você deve criar uma Medida base que será avaliada como valor.</span><span class="sxs-lookup"><span data-stu-id="02e12-113">Before creating a KPI, you must first create a Base measure that evaluates to value.</span></span> <span data-ttu-id="02e12-114">Em seguida, você estenderá a medida Base para um KPI.</span><span class="sxs-lookup"><span data-stu-id="02e12-114">You then extend the Base measure to a KPI.</span></span> <span data-ttu-id="02e12-115">A criação de medidas é descrita em outro tópico, [Criar e gerenciar medidas &#40;SSAS de Tabela&#41;](measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="02e12-115">How to create measures are described in another topic, [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md).</span></span> <span data-ttu-id="02e12-116">Um KPI também exige um valor de destino.</span><span class="sxs-lookup"><span data-stu-id="02e12-116">A KPI also requires a target value.</span></span> <span data-ttu-id="02e12-117">Este valor pode ser de outra medida pré-definida ou um valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="02e12-117">This value can be from another pre-defined measure or an absolute value.</span></span> <span data-ttu-id="02e12-118">Depois de estender uma Medida base para um KPI, você pode selecionar o valor de destino e pode definir limites de status na caixa de diálogo do Indicador chave de desempenho.</span><span class="sxs-lookup"><span data-stu-id="02e12-118">Once you have extended a Base measure to a KPI, you can then select the target value and define status thresholds in the Key Performance Indicator dialog box.</span></span>  
  
###  <a name="to-create-a-kpi"></a><a name="bkmk_create_KPI"></a> <span data-ttu-id="02e12-119">Para criar um KPI</span><span class="sxs-lookup"><span data-stu-id="02e12-119">To create a KPI</span></span>  
  
1.  <span data-ttu-id="02e12-120">Na grade de medida, clique com o botão direito do mouse na medida que servirá como a medida Base (valor) e clique em **Criar KPI**.</span><span class="sxs-lookup"><span data-stu-id="02e12-120">In the measure grid, right-click the measure that will serve as the Base measure (value), and then click **Create KPI**.</span></span>  
  
2.  <span data-ttu-id="02e12-121">Na caixa de diálogo **Indicador Chave de Desempenho** , em **Definir valor de destino**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="02e12-121">In the **Key Performance Indicator** dialog box, in **Define target value**, select from one of the following:</span></span>  
  
     <span data-ttu-id="02e12-122">Selecione **Medida**e, em seguida, selecione uma medida de destino na caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="02e12-122">Select **Measure**, and then select a target measure from the listbox.</span></span>  
  
     <span data-ttu-id="02e12-123">Selecione **Valor absoluto**e digite um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="02e12-123">Select **Absolute value**, and then type a numerical value.</span></span>  
  
3.  <span data-ttu-id="02e12-124">Em **Definir limites de status**, clique e deslize os valores de limite baixo e alto.</span><span class="sxs-lookup"><span data-stu-id="02e12-124">In **Define status thresholds**, click and slide the low and high threshold values.</span></span>  
  
4.  <span data-ttu-id="02e12-125">Em **Selecionar estilo do ícone**, clique em um tipo de imagem.</span><span class="sxs-lookup"><span data-stu-id="02e12-125">In **Select icon style**, click an image type.</span></span>  
  
5.  <span data-ttu-id="02e12-126">Clique em **Descrições**e digite as descrições para KPI, Valor, Status e Destino.</span><span class="sxs-lookup"><span data-stu-id="02e12-126">Click on **Descriptions**, and then type descriptions for KPI, Value, Status, and Target.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="02e12-127">Você pode usar o recurso Analisar no Excel para testar seu KPI.</span><span class="sxs-lookup"><span data-stu-id="02e12-127">You can use the Analyze in Excel feature to test your KPI.</span></span> <span data-ttu-id="02e12-128">Para obter mais informações, consulte [Analisar no Excel &#40;SSAS de Tabela&#41;](analyze-in-excel-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="02e12-128">For more information, see [Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md).</span></span>  
  
###  <a name="to-edit-a-kpi"></a><a name="bkmk_edit_KPI"></a> <span data-ttu-id="02e12-129">Para editar um KPI</span><span class="sxs-lookup"><span data-stu-id="02e12-129">To edit a KPI</span></span>  
  
-   <span data-ttu-id="02e12-130">Na Grade de Medida, clique com o botão direito do mouse na medida que serve como a medida base (valor) do KPI e clique em **Editar Configurações do KPI**.</span><span class="sxs-lookup"><span data-stu-id="02e12-130">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Edit KPI Settings**.</span></span>  
  
###  <a name="to-delete-a-kpi-and-the-base-measure"></a><a name="bkmk_delete"></a> <span data-ttu-id="02e12-131">Para excluir um KPI e a medida de base</span><span class="sxs-lookup"><span data-stu-id="02e12-131">To delete a KPI and the base measure</span></span>  
  
-   <span data-ttu-id="02e12-132">Na grade de medida, clique com o botão direito do mouse na medida que serve como a medida base (valor) do KPI e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="02e12-132">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete**.</span></span>  
  
###  <a name="to-delete-a-kpi-but-keep-the-base-measure"></a><a name="bkmk_delete_KPI"></a><span data-ttu-id="02e12-133">Para excluir um KPI, mas manter a medida base</span><span class="sxs-lookup"><span data-stu-id="02e12-133">To delete a KPI, but keep the base measure</span></span>  
  
-   <span data-ttu-id="02e12-134">Na grade de medida, clique com o botão direito do mouse na medida que serve como a medida base (valor) do KPI e clique em **Excluir KPI**.</span><span class="sxs-lookup"><span data-stu-id="02e12-134">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete KPI**.</span></span>  
  
## <a name="alt-shortcuts"></a><span data-ttu-id="02e12-135">Atalhos ALT</span><span class="sxs-lookup"><span data-stu-id="02e12-135">ALT Shortcuts</span></span>  
  
|<span data-ttu-id="02e12-136">Seção da Interface do Usuário</span><span class="sxs-lookup"><span data-stu-id="02e12-136">UI section</span></span>|<span data-ttu-id="02e12-137">Comando de teclas</span><span class="sxs-lookup"><span data-stu-id="02e12-137">Key command</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="02e12-138">Medida base do KPI</span><span class="sxs-lookup"><span data-stu-id="02e12-138">KPI base measure</span></span>|<span data-ttu-id="02e12-139">ALT+B</span><span class="sxs-lookup"><span data-stu-id="02e12-139">ALT+B</span></span>|  
|<span data-ttu-id="02e12-140">Status do KPI</span><span class="sxs-lookup"><span data-stu-id="02e12-140">KPI Status</span></span>|<span data-ttu-id="02e12-141">ALT+S</span><span class="sxs-lookup"><span data-stu-id="02e12-141">ALT+S</span></span>|  
|<span data-ttu-id="02e12-142">Medida</span><span class="sxs-lookup"><span data-stu-id="02e12-142">Measure</span></span>|<span data-ttu-id="02e12-143">ALT+M</span><span class="sxs-lookup"><span data-stu-id="02e12-143">ALT+M</span></span>|  
|<span data-ttu-id="02e12-144">Valor absoluto</span><span class="sxs-lookup"><span data-stu-id="02e12-144">Absolute value</span></span>|<span data-ttu-id="02e12-145">ALT+A</span><span class="sxs-lookup"><span data-stu-id="02e12-145">ALT+A</span></span>|  
|<span data-ttu-id="02e12-146">Definir limites de status</span><span class="sxs-lookup"><span data-stu-id="02e12-146">Define status thresholds</span></span>|<span data-ttu-id="02e12-147">ALT+U</span><span class="sxs-lookup"><span data-stu-id="02e12-147">ALT+U</span></span>|  
|<span data-ttu-id="02e12-148">Selecionar estilo do ícone</span><span class="sxs-lookup"><span data-stu-id="02e12-148">Select icon style</span></span>|<span data-ttu-id="02e12-149">ALT+I</span><span class="sxs-lookup"><span data-stu-id="02e12-149">ALT+I</span></span>|  
|<span data-ttu-id="02e12-150">Tendência</span><span class="sxs-lookup"><span data-stu-id="02e12-150">Trend</span></span>|<span data-ttu-id="02e12-151">ALT+T</span><span class="sxs-lookup"><span data-stu-id="02e12-151">ALT+T</span></span>|  
|<span data-ttu-id="02e12-152">Descrições</span><span class="sxs-lookup"><span data-stu-id="02e12-152">Descriptions</span></span>|<span data-ttu-id="02e12-153">ALT+D</span><span class="sxs-lookup"><span data-stu-id="02e12-153">ALT+D</span></span>|  
|<span data-ttu-id="02e12-154">Tendência</span><span class="sxs-lookup"><span data-stu-id="02e12-154">Trend</span></span>|<span data-ttu-id="02e12-155">ALT+T</span><span class="sxs-lookup"><span data-stu-id="02e12-155">ALT+T</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02e12-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="02e12-156">See Also</span></span>  
 <span data-ttu-id="02e12-157">[KPIs &#40;SSAS de tabela&#41;](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="02e12-157">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 <span data-ttu-id="02e12-158">[Medidas &#40;&#41;de tabela do SSAS](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="02e12-158">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="02e12-159">Criar e gerenciar medidas &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="02e12-159">Create and Manage Measures &#40;SSAS Tabular&#41;</span></span>](create-and-manage-measures-ssas-tabular.md)  
  
  
