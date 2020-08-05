---
title: Definir comportamento semiaditivo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- semiadditive
- Business Intelligence enhancements [Analysis Services], semiadditive behavior
- measures [Analysis Services], semiadditive
ms.assetid: b25726bc-728b-4601-ad87-9015c39dc615
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c2028c350046fdcc9f98bcd0f0612d6a91ccabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574386"
---
# <a name="define-semiadditive-behavior"></a><span data-ttu-id="ec667-102">Definir um comportamento semiaditivo</span><span class="sxs-lookup"><span data-stu-id="ec667-102">Define Semiadditive Behavior</span></span>
  <span data-ttu-id="ec667-103">Medidas semiaditivas, que não agregam uniformemente todas as dimensões, são muito comuns em muitos cenários empresariais.</span><span class="sxs-lookup"><span data-stu-id="ec667-103">Semiadditive measures, which do not uniformly aggregate across all dimensions, are very common in many business scenarios.</span></span> <span data-ttu-id="ec667-104">Todo cubo que se baseia em instantâneos de balanços, com o decorrer do tempo, apresenta esse problema.</span><span class="sxs-lookup"><span data-stu-id="ec667-104">Every cube that is based on snapshots of balances over time exhibits this problem.</span></span> <span data-ttu-id="ec667-105">Você encontra esses instantâneos em aplicativos que cuidam de títulos, saldos de contas, orçamentos, recursos humanos, apólices de seguros e sinistros e em vários outros domínios empresariais.</span><span class="sxs-lookup"><span data-stu-id="ec667-105">You can find these snapshots in applications dealing with securities, account balances, budgeting, human resources, insurance policies and claims, and many other business domains.</span></span>  
  
 <span data-ttu-id="ec667-106">Adicione um comportamento semiaditivo a um cubo para definir um método de agregação para medidas ou membros individuais de um atributo de tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="ec667-106">Add semiadditive behavior to a cube to define an aggregation method for individual measures or members of the account type attribute.</span></span> <span data-ttu-id="ec667-107">Se o cubo contiver uma dimensão de conta, é possível definir automaticamente o comportamento semiaditivo de acordo com o tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="ec667-107">If the cube contains an account dimension, you can automatically set semiadditive behavior based on the account type.</span></span>  
  
 <span data-ttu-id="ec667-108">Para adicionar um comportamento semiaditivo, abra um cubo no Designer de Cubo e escolha **Adicionar Business Intelligence** no menu Cubo.</span><span class="sxs-lookup"><span data-stu-id="ec667-108">To add semiadditive behavior, open a cube in Cube Designer and choose **Add Business Intelligence** from the Cube menu.</span></span> <span data-ttu-id="ec667-109">No Assistente de Business Intelligence, selecione a opção **Definir comportamento semiaditivo** na página **Escolher Aprimoramento** .</span><span class="sxs-lookup"><span data-stu-id="ec667-109">In the Business Intelligence Wizard, select the **Define semiadditive behavior** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="ec667-110">Esse assistente orienta você pelas etapas para identificar quais medidas têm comportamento semiaditivo.</span><span class="sxs-lookup"><span data-stu-id="ec667-110">This wizard then guides you through the steps of identifying which measures have semiadditive behavior.</span></span>  
  
 <span data-ttu-id="ec667-111">Com exceção de LastChild que está disponível na edição standard, os comportamentos semiaditivos só estão disponíveis nas edições business intelligence ou enterprise.</span><span class="sxs-lookup"><span data-stu-id="ec667-111">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span>  
  
## <a name="define-semiadditive-behavior"></a><span data-ttu-id="ec667-112">Definir um comportamento semiaditivo</span><span class="sxs-lookup"><span data-stu-id="ec667-112">Define Semiadditive Behavior</span></span>  
 <span data-ttu-id="ec667-113">Na página **Definir Comportamento Semiaditivo** do assistente, selecione como definir o aspecto semiaditivo selecionando uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="ec667-113">On the **Define Semiadditive Behavior** page of the wizard, you select how to define semiadditivity by selecting one of the following options:</span></span>  
  
 <span data-ttu-id="ec667-114">**Desativar comportamento semiaditivo**</span><span class="sxs-lookup"><span data-stu-id="ec667-114">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="ec667-115">Remove o comportamento semiaditivo de um cubo no qual ele foi previamente definido.</span><span class="sxs-lookup"><span data-stu-id="ec667-115">Removes semiadditive behavior from a cube in which semiadditive behavior was previously defined.</span></span> <span data-ttu-id="ec667-116">Essa seleção redefinirá uma medida como `SUM` se ela estiver configurada como algum destes tipos de função de agregação:</span><span class="sxs-lookup"><span data-stu-id="ec667-116">This selection resets a measure to `SUM` if it is set to any of the following aggregation function types:</span></span>  
  
-   <span data-ttu-id="ec667-117">Por Conta</span><span class="sxs-lookup"><span data-stu-id="ec667-117">By Account</span></span>  
  
-   <span data-ttu-id="ec667-118">Average of Children</span><span class="sxs-lookup"><span data-stu-id="ec667-118">Average of Children</span></span>  
  
-   <span data-ttu-id="ec667-119">First Child</span><span class="sxs-lookup"><span data-stu-id="ec667-119">First Child</span></span>  
  
-   <span data-ttu-id="ec667-120">Último Filho</span><span class="sxs-lookup"><span data-stu-id="ec667-120">Last Child</span></span>  
  
-   <span data-ttu-id="ec667-121">Último Filho Não Vazio</span><span class="sxs-lookup"><span data-stu-id="ec667-121">Last Nonempty Child</span></span>  
  
-   <span data-ttu-id="ec667-122">Primeiro Filho Não Vazio</span><span class="sxs-lookup"><span data-stu-id="ec667-122">First Nonempty Child</span></span>  
  
-   <span data-ttu-id="ec667-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ec667-123">None</span></span>  
  
 <span data-ttu-id="ec667-124">Essa opção não altera as medidas com uma função de agregação regular:,,, `Sum` `Min` `Max` `Count` ou `Distinct``Count` .</span><span class="sxs-lookup"><span data-stu-id="ec667-124">This option does not change measures with a regular aggregation function: `Sum`, `Min`, `Max`, `Count`, or `Distinct``Count`.</span></span>  
  
 <span data-ttu-id="ec667-125">**O assistente detectou a dimensão de conta ' account ', que contém membros semiaditivos. O servidor agregará membros dessa dimensão de acordo com o comportamento semiaditivo especificado para cada tipo de conta.**</span><span class="sxs-lookup"><span data-stu-id="ec667-125">**The wizard has detected the 'Account" account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="ec667-126">Faz com que o sistema configure todas as medidas de um grupo de medidas de uma dimensão por uma dimensão do tipo Conta para a função de agregação Por Conta e o servidor agregará os membros da dimensão de acordo com o comportamento semiaditivo especificado para cada tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="ec667-126">Causes the system to set all measures from a measure group dimensioned by an Account type dimension to the By Account aggregation function and the server will aggregate members of the dimension according to the semiadditive behavior specified for each account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec667-127">Essa opção será selecionada por padrão se o assistente detectar uma dimensão de tipo Conta.</span><span class="sxs-lookup"><span data-stu-id="ec667-127">This option is selected by default if the wizard detects an Account type dimension.</span></span>  
  
 <span data-ttu-id="ec667-128">**Definir comportamento semiaditivo para medidas individuais**</span><span class="sxs-lookup"><span data-stu-id="ec667-128">**Define semiadditive behavior for individual measures**</span></span>  
 <span data-ttu-id="ec667-129">Seleciona o comportamento semiaditivo de cada medida individualmente.</span><span class="sxs-lookup"><span data-stu-id="ec667-129">Selects the semiadditive behavior of each measure individually.</span></span> <span data-ttu-id="ec667-130">A configuração padrão é `SUM` (completamente aditivo).</span><span class="sxs-lookup"><span data-stu-id="ec667-130">The default setting is `SUM` (fully additive).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec667-131">Essa opção será selecionada por padrão se o assistente não detectar uma dimensão de tipo Conta.</span><span class="sxs-lookup"><span data-stu-id="ec667-131">This option is selected by default if the wizard does not detect an Account type dimension.</span></span>  
  
 <span data-ttu-id="ec667-132">Para cada medida, você pode selecionar um dos tipos de funcionalidade semiaditiva descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ec667-132">For each measure, you can select from the types of semiadditive functionality described in the following table.</span></span>  
  
|<span data-ttu-id="ec667-133">Função semiaditiva</span><span class="sxs-lookup"><span data-stu-id="ec667-133">Semiadditive function</span></span>|<span data-ttu-id="ec667-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec667-134">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="ec667-135">Average of Children</span><span class="sxs-lookup"><span data-stu-id="ec667-135">Average of Children</span></span>|<span data-ttu-id="ec667-136">A agregação de um membro é a média de seus filhos.</span><span class="sxs-lookup"><span data-stu-id="ec667-136">The aggregation of a member is the average of its children.</span></span>|  
|<span data-ttu-id="ec667-137">ByAccount</span><span class="sxs-lookup"><span data-stu-id="ec667-137">ByAccount</span></span>|<span data-ttu-id="ec667-138">O sistema lê o comportamento de semiaditivo especificado para o tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="ec667-138">The system reads the semiadditive behavior specified for the account type.</span></span>|  
|<span data-ttu-id="ec667-139">Contagem</span><span class="sxs-lookup"><span data-stu-id="ec667-139">Count</span></span>|<span data-ttu-id="ec667-140">A agregação é uma contagem de membros.</span><span class="sxs-lookup"><span data-stu-id="ec667-140">The aggregation is a count of members.</span></span>|  
|<span data-ttu-id="ec667-141">Contagem Distinta</span><span class="sxs-lookup"><span data-stu-id="ec667-141">Distinct Count</span></span>|<span data-ttu-id="ec667-142">A agregação é uma contagem de membros exclusivos.</span><span class="sxs-lookup"><span data-stu-id="ec667-142">The aggregation is a count of unique members.</span></span>|  
|<span data-ttu-id="ec667-143">First Child</span><span class="sxs-lookup"><span data-stu-id="ec667-143">First Child</span></span>|<span data-ttu-id="ec667-144">O valor do membro é avaliado como o valor de seu primeiro filho juntamente com a dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="ec667-144">The member value is evaluated as the value of its first child along the time dimension.</span></span>|  
|<span data-ttu-id="ec667-145">FirstNonEmpty</span><span class="sxs-lookup"><span data-stu-id="ec667-145">FirstNonEmpty</span></span>|<span data-ttu-id="ec667-146">O valor do membro é avaliado como o valor de seu primeiro filho juntamente com a dimensão que contém dados.</span><span class="sxs-lookup"><span data-stu-id="ec667-146">The member value is evaluated as the value of its first child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="ec667-147">LastChild</span><span class="sxs-lookup"><span data-stu-id="ec667-147">LastChild</span></span>|<span data-ttu-id="ec667-148">O valor do membro é avaliado como o valor de seu último filho juntamente com a dimensão de tempo.</span><span class="sxs-lookup"><span data-stu-id="ec667-148">The member value is evaluated as the value of its last child along the time dimension.</span></span>|  
|<span data-ttu-id="ec667-149">LastNonEmpty</span><span class="sxs-lookup"><span data-stu-id="ec667-149">LastNonEmpty</span></span>|<span data-ttu-id="ec667-150">O valor do membro é avaliado como o valor de seu último filho juntamente com a dimensão que contém dados.</span><span class="sxs-lookup"><span data-stu-id="ec667-150">The member value is evaluated as the value of its last child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="ec667-151">Max</span><span class="sxs-lookup"><span data-stu-id="ec667-151">Max</span></span>|<span data-ttu-id="ec667-152">A função de agregação máxima é aplicada.</span><span class="sxs-lookup"><span data-stu-id="ec667-152">The standard maximum aggregation function is applied.</span></span>|  
|<span data-ttu-id="ec667-153">Mín</span><span class="sxs-lookup"><span data-stu-id="ec667-153">Min</span></span>|<span data-ttu-id="ec667-154">A função de agregação mínima é aplicada.</span><span class="sxs-lookup"><span data-stu-id="ec667-154">The standard minimum aggregation function is applied.</span></span>|  
|<span data-ttu-id="ec667-155">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ec667-155">None</span></span>|<span data-ttu-id="ec667-156">Nenhuma agregação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="ec667-156">No aggregation is applied.</span></span>|  
|<span data-ttu-id="ec667-157">Somar</span><span class="sxs-lookup"><span data-stu-id="ec667-157">Sum</span></span>|<span data-ttu-id="ec667-158">A função de soma padrão é aplicada.</span><span class="sxs-lookup"><span data-stu-id="ec667-158">The standard summation function is applied.</span></span>|  
  
 <span data-ttu-id="ec667-159">Qualquer comportamento semiaditivo existente será substituído quando você concluir o assistente.</span><span class="sxs-lookup"><span data-stu-id="ec667-159">Any existing semiadditive behavior is overwritten when you complete the wizard.</span></span>  
  
  
