---
title: Alterar os ícones de indicadores e os conjuntos de indicadores (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8a056adf-4473-473d-9b0c-314675af7bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 398d21319ab6da22f2b10c3607baf8f110d6e65b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684069"
---
# <a name="change-indicator-icons-and-indicator-sets-report-builder-and-ssrs"></a><span data-ttu-id="25e8a-102">Alterar os ícones de indicadores e os conjuntos de indicadores (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="25e8a-102">Change Indicator Icons and Indicator Sets (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="25e8a-103">O  fornece conjuntos de indicadores pré-configurados, que talvez nem sempre descrevam seus dados de modo eficiente e funcionem bem no relatório produzido.</span><span class="sxs-lookup"><span data-stu-id="25e8a-103">provides preconfigured indicators sets, which might not always depict your data effectively and work well in the delivered report.</span></span> <span data-ttu-id="25e8a-104">Este tópico fornece procedimentos para alterar a aparência de ícones de indicador e alterar os conjuntos de indicadores para incluir ícones de indicadores diferentes e mais ou menos ícones.</span><span class="sxs-lookup"><span data-stu-id="25e8a-104">This topic provides procedures to change the appearance of indicator icons and change the indicator sets to include different, more, or fewer indicator icons.</span></span>  
  
 <span data-ttu-id="25e8a-105">Opções como cores podem ser definidas com o uso de expressões.</span><span class="sxs-lookup"><span data-stu-id="25e8a-105">Options such as colors can be set by using expressions.</span></span> <span data-ttu-id="25e8a-106">Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="25e8a-106">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-color-of-an-indicator-icon"></a><span data-ttu-id="25e8a-107">Para alterar a cor de um ícone de indicador</span><span class="sxs-lookup"><span data-stu-id="25e8a-107">To change the color of an indicator icon</span></span>  
  
1.  <span data-ttu-id="25e8a-108">Clique com o botão direito do mouse no indicador que você deseja alterar e clique em **Propriedades do Indicador**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-108">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="25e8a-109">Clique em **Valores e Estados** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="25e8a-109">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="25e8a-110">Clique na seta para baixo na coluna **Cor** ao lado do ícone que você deseja alterar e clique na cor a ser usada, **Sem Cor**ou **Mais cores**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-110">Click the down arrow in the **Color** column next to the icon that you want to change and click the color to use, **No Color**, or **More colors**.</span></span>  
  
     <span data-ttu-id="25e8a-111">Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define o valor da opção **Cor** .</span><span class="sxs-lookup"><span data-stu-id="25e8a-111">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Color** option.</span></span>  
  
     <span data-ttu-id="25e8a-112">Se você clicou em **Mais Cores**, a caixa de diálogo **Selecionar Cor** é aberta, na qual é possível escolher de uma ampla gama de cores.</span><span class="sxs-lookup"><span data-stu-id="25e8a-112">If you clicked **More Colors**, the **Select Color** dialog box opens, where you can choose from a wide array of colors.</span></span> <span data-ttu-id="25e8a-113">Para obter mais informações sobre suas opções, consulte [Caixa de diálogo Selecionar Cor &#40;Construtor de Relatórios e SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="25e8a-113">For more information about its options, see [Select Color Dialog Box &#40;Report Builder and SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="25e8a-114">Clique em **OK** para fechar a caixa de diálogo **Selecionar Cor** .</span><span class="sxs-lookup"><span data-stu-id="25e8a-114">Click **OK** to close the **Select Color** dialog box.</span></span>  
  
4.  <span data-ttu-id="25e8a-115">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-115">Click **OK**.</span></span>  
  
### <a name="to-change-the-icon"></a><span data-ttu-id="25e8a-116">Para alterar o ícone</span><span class="sxs-lookup"><span data-stu-id="25e8a-116">To change the icon</span></span>  
  
1.  <span data-ttu-id="25e8a-117">Clique com o botão direito do mouse no indicador que você deseja alterar e clique em **Propriedades do Indicador**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-117">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="25e8a-118">Clique em **Valores e Estados** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="25e8a-118">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="25e8a-119">Clique na seta para baixo ao lado do ícone que você deseja alterar e selecione outro ícone.</span><span class="sxs-lookup"><span data-stu-id="25e8a-119">Click the down arrow next to the icon that you want to change and select a different icon.</span></span>  
  
     <span data-ttu-id="25e8a-120">Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define o valor da opção **Ícone** .</span><span class="sxs-lookup"><span data-stu-id="25e8a-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Icon** option.</span></span>  
  
4.  <span data-ttu-id="25e8a-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-121">Click **OK**.</span></span>  
  
### <a name="to-use-a-custom-image-as-an-indicator-icon"></a><span data-ttu-id="25e8a-122">Para usar uma imagem personalizada como um ícone de indicador</span><span class="sxs-lookup"><span data-stu-id="25e8a-122">To use a custom image as an indicator icon</span></span>  
  
1.  <span data-ttu-id="25e8a-123">Clique com o botão direito do mouse no indicador que você deseja alterar e clique em **Propriedades do Indicador**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="25e8a-124">Clique em **Valores e Estados** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="25e8a-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="25e8a-125">Clique na seta para baixo ao lado do ícone que você deseja alterar e selecione **Imagem**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-125">Click the down arrow next to the icon that you wan to change and select **Image**.</span></span>  
  
4.  <span data-ttu-id="25e8a-126">Na lista **Selecionar a origem da imagem** , clique em **Externa**, **Inserida**ou **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-126">In the **Select the image source** list, click **External**, **Embedded**, or **Database**.</span></span>  
  
5.  <span data-ttu-id="25e8a-127">Dependendo da origem da imagem, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="25e8a-127">Depending on the source of the image, do the one of the following:</span></span>  
  
    -   <span data-ttu-id="25e8a-128">Para usar uma imagem armazenada externamente ao relatório, clique em **Procurar** e localize a imagem.</span><span class="sxs-lookup"><span data-stu-id="25e8a-128">To use an image that is stored externally to the report, click **Browse** and locate the image.</span></span> <span data-ttu-id="25e8a-129">O relatório incluirá uma referência para a imagem.</span><span class="sxs-lookup"><span data-stu-id="25e8a-129">The report will include a reference to the image.</span></span>  
  
    -   <span data-ttu-id="25e8a-130">Para usar uma imagem inserida no relatório, clique em **Importar** e localize a imagem.</span><span class="sxs-lookup"><span data-stu-id="25e8a-130">To use an image that is embedded in the report, click **Import** and locate the image.</span></span> <span data-ttu-id="25e8a-131">A imagem será adicionada à definição de relatório e salva com ela.</span><span class="sxs-lookup"><span data-stu-id="25e8a-131">The image will be added to the report definition and saved with it.</span></span>  
  
    -   <span data-ttu-id="25e8a-132">Para usar uma imagem que esteja em um banco de dados, na lista **Usar este campo** .</span><span class="sxs-lookup"><span data-stu-id="25e8a-132">To use an image that is in a database, in the **Use this field** list.</span></span> <span data-ttu-id="25e8a-133">Selecione o campo na lista e, na lista **Usar este tipo MIME** , selecione o tipo MIME da imagem.</span><span class="sxs-lookup"><span data-stu-id="25e8a-133">select the field from the list and then in the **Use this MIME type** list, select the MIME type of the image.</span></span>  
  
6.  <span data-ttu-id="25e8a-134">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-134">Click **OK**.</span></span>  
  
### <a name="to-add-an-icon-to-the-indicator-set"></a><span data-ttu-id="25e8a-135">Para adicionar um ícone ao conjunto de indicadores</span><span class="sxs-lookup"><span data-stu-id="25e8a-135">To add an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="25e8a-136">Clique com o botão direito do mouse no indicador que você deseja alterar e clique em **Propriedades do Indicador**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-136">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="25e8a-137">Clique em **Valores e Estados** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="25e8a-137">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="25e8a-138">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-138">Click **Add**.</span></span> <span data-ttu-id="25e8a-139">Um indicador é adicionado, usando o ícone padrão e a opção **Sem Cor** .</span><span class="sxs-lookup"><span data-stu-id="25e8a-139">An indicator is added, using the default icon and the **No Color** option.</span></span>  
  
     <span data-ttu-id="25e8a-140">Configure o indicador para usar a cor e o ícone desejado.</span><span class="sxs-lookup"><span data-stu-id="25e8a-140">Configure the indictor to use the icon and color you want.</span></span> <span data-ttu-id="25e8a-141">Os procedimentos anteriores neste tópico descrevem a etapa para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="25e8a-141">Procedures earlier in this topic describe the steps to do this.</span></span>  
  
4.  <span data-ttu-id="25e8a-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-142">Click **OK**.</span></span>  
  
### <a name="to-delete-an-icon-to-the-indicator-set"></a><span data-ttu-id="25e8a-143">Para excluir um ícone do conjunto de indicadores</span><span class="sxs-lookup"><span data-stu-id="25e8a-143">To delete an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="25e8a-144">Clique com o botão direito do mouse no indicador que você deseja alterar e clique em **Propriedades do Indicador**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-144">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="25e8a-145">Clique em **Valores e Estados** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="25e8a-145">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="25e8a-146">Selecione o ícone a ser excluído e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-146">Select the icon to delete, and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="25e8a-147">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="25e8a-147">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e8a-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25e8a-148">See Also</span></span>  
 [<span data-ttu-id="25e8a-149">Indicadores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="25e8a-149">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
