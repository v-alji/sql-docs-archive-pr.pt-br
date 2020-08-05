---
title: Grupos de medidas vinculados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- linked measure groups [Analysis Services]
- referencing measure groups
- Linked Measure Group Wizard
- measure groups [Analysis Services], linked
- linked dimensions [Analysis Services]
ms.assetid: 7f838452-8669-4194-8e15-7afdc7f15251
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2a7d7443b8c25f5cbafa5af83364ef05d8053145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574371"
---
# <a name="linked-measure-groups"></a><span data-ttu-id="51434-102">Grupos de medidas vinculados</span><span class="sxs-lookup"><span data-stu-id="51434-102">Linked Measure Groups</span></span>
  <span data-ttu-id="51434-103">Um grupo de medidas vinculado se baseia em outro grupo de medidas em um cubo diferente no mesmo banco de dados ou em um banco de dados diferente do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="51434-103">A linked measure group is based on another measure group in a different cube within the same database or a different Analysis Services database.</span></span> <span data-ttu-id="51434-104">Você poderá usar um grupo de medidas vinculado se quiser reutilizar um conjunto de medidas, e os valores de dados correspondentes, em vários cubos.</span><span class="sxs-lookup"><span data-stu-id="51434-104">You might use a linked measure group if you want to reuse a set of measures, and the corresponding data values, in multiple cubes.</span></span>  
  
 <span data-ttu-id="51434-105">A Microsoft recomenda que os grupos de medidas vinculados e originais residam em soluções executadas no mesmo servidor.</span><span class="sxs-lookup"><span data-stu-id="51434-105">Microsoft recommends that the original and linked measure groups reside in solutions that run on the same server.</span></span> <span data-ttu-id="51434-106">A vinculação a um grupo de medidas em um servidor remoto está agendada para substituição em uma versão futura (consulte [recursos de Analysis Services preteridos no SQL Server 2014](../deprecated-analysis-services-features-in-sql-server-2014.md)).</span><span class="sxs-lookup"><span data-stu-id="51434-106">Linking to a measure group on a remote server is scheduled for deprecation in a future release (see [Deprecated Analysis Services Features in SQL Server 2014](../deprecated-analysis-services-features-in-sql-server-2014.md)).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="51434-107">Os grupos de medidas vinculados são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="51434-107">Linked measure groups are read-only.</span></span> <span data-ttu-id="51434-108">Para obter as alterações mais recentes, você deve excluir e recriar todos os grupos de medidas vinculados com base no objeto de origem modificado.</span><span class="sxs-lookup"><span data-stu-id="51434-108">To pick up the latest changes, you must delete and recreate all linked measure groups based on the modified source object.</span></span> <span data-ttu-id="51434-109">Por esse motivo, copiar e colar os grupos de medidas entre projetos é uma abordagem alternativa que você deve considerar no caso da necessidade de alterações futuras ao grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="51434-109">For this reason, copy and pasting measure groups between projects is an alternative approach that you should consider in case future modifications to the measure group are required.</span></span>  
  
## <a name="usage-limitations"></a><span data-ttu-id="51434-110">Limitações de uso</span><span class="sxs-lookup"><span data-stu-id="51434-110">Usage Limitations</span></span>  
 <span data-ttu-id="51434-111">Como observado anteriormente, uma restrição importante ao uso de medidas vinculadas é uma incapacidade de personalizar uma medida vinculada diretamente.</span><span class="sxs-lookup"><span data-stu-id="51434-111">As noted previously, an important constraint to using linked measures is an inability to customize a linked measure directly.</span></span> <span data-ttu-id="51434-112">As modificações no tipo de dados, no formato, na associação de dados e na visibilidade, bem como a associação dos itens no próprio grupo de medidas, são alterações que devem ser feitas no grupo de medidas original.</span><span class="sxs-lookup"><span data-stu-id="51434-112">Modifications to the data type, format, data binding, and visibility, as well as membership of the items in the measure group itself, are all changes that must be made in the original measure group.</span></span>  
  
 <span data-ttu-id="51434-113">Operacionalmente, os grupos de medidas vinculados são idênticos a outros grupos de medidas, quando acessados por aplicativos cliente e são consultados da mesma maneira que outros grupos de medidas.</span><span class="sxs-lookup"><span data-stu-id="51434-113">Operationally, linked measure groups are identical to other measure groups when accessed by client applications, and are queried in the same manner as other measure groups.</span></span>  
  
 <span data-ttu-id="51434-114">Quando você consulta um cubo que contenha um grupo de medidas vinculado, o vínculo é estabelecido e resolvido durante a primeira fase de cálculo do cubo de destino.</span><span class="sxs-lookup"><span data-stu-id="51434-114">When you query a cube that contains a linked measure group, the link is established and resolved during the first calculation pass of the destination cube.</span></span> <span data-ttu-id="51434-115">Devido a esse comportamento, qualquer cálculo armazenado no grupo de medidas vinculado não pode ser resolvido antes que a consulta seja avaliada.</span><span class="sxs-lookup"><span data-stu-id="51434-115">Because of this behavior, any calculations that are stored in the linked measure group cannot be resolved before the query is evaluated.</span></span> <span data-ttu-id="51434-116">Em outras palavras, as medidas e células calculadas devem ser recriadas no cubo de destino em vez de herdadas do cubo de origem.</span><span class="sxs-lookup"><span data-stu-id="51434-116">In other words, calculated measures and calculated cells must be recreated in the destination cube rather than inherited from the source cube.</span></span>  
  
 <span data-ttu-id="51434-117">A lista a seguir resume as limitações de uso.</span><span class="sxs-lookup"><span data-stu-id="51434-117">The following list summarizes usage limitations.</span></span>  
  
-   <span data-ttu-id="51434-118">Você não pode criar um grupo de medidas vinculado a partir de outro grupo de medidas vinculado.</span><span class="sxs-lookup"><span data-stu-id="51434-118">You cannot create a linked measure group from another linked measure group.</span></span>  
  
-   <span data-ttu-id="51434-119">Você não pode adicionar ou remover medidas em um grupo de medidas vinculado.</span><span class="sxs-lookup"><span data-stu-id="51434-119">You cannot add or remove measures in a linked measure group.</span></span> <span data-ttu-id="51434-120">A associação é definida somente no grupo de medidas original.</span><span class="sxs-lookup"><span data-stu-id="51434-120">Membership is defined only in the original measure group.</span></span>  
  
-   <span data-ttu-id="51434-121">Não há suporte a write-back nos grupos de medidas vinculados.</span><span class="sxs-lookup"><span data-stu-id="51434-121">Writeback is not supported in linked measure groups.</span></span>  
  
-   <span data-ttu-id="51434-122">Os grupos de medidas vinculados não podem ser usados em vários relacionamentos muitos para muitos, especialmente quando esses relacionamentos estiverem em cubos diferentes.</span><span class="sxs-lookup"><span data-stu-id="51434-122">Linked measure groups cannot be used in multiple many-to-many relationships, especially when those relationships are in different cubes.</span></span> <span data-ttu-id="51434-123">Fazer isso poderá resultar em agregações ambíguas.</span><span class="sxs-lookup"><span data-stu-id="51434-123">Doing so can result in ambiguous aggregations.</span></span> <span data-ttu-id="51434-124">Para obter mais informações, consulte [Incorrect Amounts for Linked Measures in Cubes containing Many-to-Many Relationships](https://social.technet.microsoft.com/wiki/contents/articles/22911.incorrect-amounts-for-linked-measures-in-cubes-containing-many-to-many-relationships-ssas-troubleshooting.aspx)(Quantidades incorretas de medidas vinculadas em cubos com relacionamentos muitos para muitos).</span><span class="sxs-lookup"><span data-stu-id="51434-124">For more information, see [Incorrect Amounts for Linked Measures in Cubes containing Many-to-Many Relationships](https://social.technet.microsoft.com/wiki/contents/articles/22911.incorrect-amounts-for-linked-measures-in-cubes-containing-many-to-many-relationships-ssas-troubleshooting.aspx).</span></span>  
  
 <span data-ttu-id="51434-125">As medidas contidas em um grupo de medidas vinculado podem ser diretamente organizadas apenas junto com dimensões vinculados recuperadas do mesmo banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="51434-125">The measures contained in a linked measure group can be directly organized only along linked dimensions retrieved from the same [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="51434-126">No entanto, você pode usar membros calculados para relacionar informações de grupos de medidas vinculados a outras dimensões não vinculadas no cubo.</span><span class="sxs-lookup"><span data-stu-id="51434-126">However, you can use calculated members to relate information from linked measure groups to the other, non-linked dimensions in your cube.</span></span> <span data-ttu-id="51434-127">Você também pode usar uma relação indireta, como um referência ou relação muitos para muitos, para relacionar dimensões não vinculadas a um grupo de medidas vinculado.</span><span class="sxs-lookup"><span data-stu-id="51434-127">You can also use an indirect relationship, such as a reference or many-to-many relationship, to relate non-linked dimensions to a linked measure group.</span></span>  
  
## <a name="create-or-modify-a-linked-measure"></a><span data-ttu-id="51434-128">Criar ou modificar uma medida vinculada</span><span class="sxs-lookup"><span data-stu-id="51434-128">Create or modify a linked measure</span></span>  
 <span data-ttu-id="51434-129">Use o [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] para criar um grupo de medidas vinculado.</span><span class="sxs-lookup"><span data-stu-id="51434-129">Use [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] to create a linked measure group.</span></span>  
  
1.  <span data-ttu-id="51434-130">Finalize qualquer modificação feita no grupo de medidas original agora, no cubo de origem, de forma que você não precise recriar os grupos de medidas vinculados posteriormente em cubos subsequentes.</span><span class="sxs-lookup"><span data-stu-id="51434-130">Finalize any modifications to the original measure group now, in the source cube, so that you don't have to recreate the linked measure groups later in subsequent cubes.</span></span> <span data-ttu-id="51434-131">Você pode renomear um objeto vinculado, mas não pode alterar qualquer outra propriedade.</span><span class="sxs-lookup"><span data-stu-id="51434-131">You can rename a linked object, but you cannot change any other properties.</span></span>  
  
2.  <span data-ttu-id="51434-132">No Gerenciador de Soluções, clique duas vezes no cubo ao qual você está adicionando o grupo de medidas vinculado.</span><span class="sxs-lookup"><span data-stu-id="51434-132">In Solution Explorer, double-click the cube to which you are adding the linked measure group.</span></span> <span data-ttu-id="51434-133">Esta etapa abre o cubo no Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="51434-133">This step opens the cube in Cube Designer.</span></span>  
  
3.  <span data-ttu-id="51434-134">No Designer de Cubo, no painel Medidas ou no painel Dimensões, clique com o botão direito do mouse em um dos painéis e selecione **Novo Objeto Vinculado**.</span><span class="sxs-lookup"><span data-stu-id="51434-134">In Cube Designer, in either the Measures pane or Dimensions pane, right-click anywhere in either pane, then select **New Linked Object**.</span></span> <span data-ttu-id="51434-135">Isso iniciará o Assistente para Objetos Vinculados.</span><span class="sxs-lookup"><span data-stu-id="51434-135">This starts the Linked Object Wizard.</span></span>  
  
4.  <span data-ttu-id="51434-136">Na primeira página, especifique a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="51434-136">On the first page, specify the data source.</span></span> <span data-ttu-id="51434-137">Esta etapa confirma o local do grupo de medidas original.</span><span class="sxs-lookup"><span data-stu-id="51434-137">This step establishes the location of the original measure group.</span></span> <span data-ttu-id="51434-138">O padrão é o cubo atual no banco de dados atual, mas você também pode escolher um banco de dados do Analysis Services diferente.</span><span class="sxs-lookup"><span data-stu-id="51434-138">The default is the current cube in the current database, but you can also choose a different Analysis Services database.</span></span>  
  
5.  <span data-ttu-id="51434-139">Na página seguinte, escolha o grupo de medidas ou a dimensão que você deseja vincular.</span><span class="sxs-lookup"><span data-stu-id="51434-139">On the next page, choose the measure group or dimension you want to link.</span></span> <span data-ttu-id="51434-140">Os objetos de Dimensões e do Cubo, como grupos de medidas, são listados separadamente.</span><span class="sxs-lookup"><span data-stu-id="51434-140">Dimensions and Cube objects, such as measure groups, are listed separately.</span></span> <span data-ttu-id="51434-141">Somente os objetos que ainda não estejam presentes no cubo atual estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="51434-141">Only those objects not already present in the current cube are available.</span></span>  
  
6.  <span data-ttu-id="51434-142">Clique em **Concluir** para criar o objeto vinculado.</span><span class="sxs-lookup"><span data-stu-id="51434-142">Click **Finish** to create the linked object.</span></span> <span data-ttu-id="51434-143">Os objetos vinculados aparecem no painel Medidas e Dimensões, indicados pelo ícone de link.</span><span class="sxs-lookup"><span data-stu-id="51434-143">Linked objects appear in the Measures and Dimensions pane, indicated by the link icon.</span></span>  
  
## <a name="secure-a-linked-measure"></a><span data-ttu-id="51434-144">Proteger uma medida vinculada</span><span class="sxs-lookup"><span data-stu-id="51434-144">Secure a linked measure</span></span>  
 <span data-ttu-id="51434-145">Depois que o vínculo tiver sido definido, o acesso às medidas em um grupo de medidas vinculado será gerenciado da mesma maneira que o acesso aos outros grupos de medidas.</span><span class="sxs-lookup"><span data-stu-id="51434-145">After the link has been defined, access to the measures in a linked measure group, is managed in the same manner as access to other measure groups.</span></span> <span data-ttu-id="51434-146">Um objeto vinculado aparece ao lado de suas contrapartes não vinculadas no Designer de Função.</span><span class="sxs-lookup"><span data-stu-id="51434-146">A linked object appears alongside its non-linked counterparts in Role Designer.</span></span> <span data-ttu-id="51434-147">Para obter mais informações sobre como gerenciar a segurança de um grupo de medidas, consulte [Conceder permissões de cubo ou modelo &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="51434-147">For more information on managing security for a measure group, see [Grant cube or model permissions &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md).</span></span>  
  
 <span data-ttu-id="51434-148">Para definir ou usar um grupo de medidas vinculado, a conta de serviço do Windows para a instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deve pertencer a uma função de banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que tenha direitos de acesso de `ReadDefinition` e `Read` para a instância de origem do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para o cubo de origem e grupo de medidas ou deve pertencer à função [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] da instância de origem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51434-148">In order to define or use a linked measure group, the Windows service account for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance must belong to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database role that has `ReadDefinition` and `Read` access rights on the source [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to the source cube and measure group, or must belong to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Administrators role for the source [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51434-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51434-149">See Also</span></span>  
 [<span data-ttu-id="51434-150">Definir dimensões vinculadas</span><span class="sxs-lookup"><span data-stu-id="51434-150">Define Linked Dimensions</span></span>](define-linked-dimensions.md)  
  
  