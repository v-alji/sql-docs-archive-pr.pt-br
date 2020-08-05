---
title: Definir a orientação da caixa de texto (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 64bd53f4-2f31-4732-8c2e-64c7b54b6972
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d509f1df29203fa5def79b61b74ae9db8f40d204
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569084"
---
# <a name="set-text-box-orientation-report-builder-and-ssrs"></a><span data-ttu-id="54a24-102">Definir a orientação da caixa de texto (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="54a24-102">Set Text Box Orientation (Report Builder and SSRS)</span></span>
  <span data-ttu-id="54a24-103">Uma caixa de texto pode ser orientada em direções diferentes: horizontalmente, verticalmente (texto lido de cima para baixo) ou girado 270 graus (texto lido de baixo para cima).</span><span class="sxs-lookup"><span data-stu-id="54a24-103">A text box can be oriented in different directions: horizontally, vertically (text reading from top to bottom), or rotated by 270 degrees (text reading from bottom to top).</span></span> <span data-ttu-id="54a24-104">Como a orientação é definida na caixa de texto, não no texto, ela se aplica a todo o texto na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="54a24-104">Because orientation is set on the text box not the text, the orientation applies to all the text in the text box.</span></span> <span data-ttu-id="54a24-105">Você não pode especificar orientações diferentes para partes do texto.</span><span class="sxs-lookup"><span data-stu-id="54a24-105">You cannot specify different orientations for parts of the text.</span></span> <span data-ttu-id="54a24-106">Dimensione manualmente a largura da coluna e a altura da linha para acomodar o texto girado.</span><span class="sxs-lookup"><span data-stu-id="54a24-106">Size the column width and the row height manually to accommodate the rotated text.</span></span>  
  
 <span data-ttu-id="54a24-107">A propriedade WritingMode, que você usa para especificar a orientação do texto, não está disponível na caixa de diálogo **Propriedades da caixa de texto** .</span><span class="sxs-lookup"><span data-stu-id="54a24-107">The WritingMode property, which you use to specify text orientation, is not available in the **Text Box Properties** dialog box.</span></span> <span data-ttu-id="54a24-108">Abra o painel Propriedades e defina a propriedade.</span><span class="sxs-lookup"><span data-stu-id="54a24-108">You need to open the Properties pane and set the property there.</span></span> <span data-ttu-id="54a24-109">Os valores disponíveis para a propriedade WritingMode são **horizontal** (leitura de texto da esquerda para a direita), **vertical** (leitura de texto de cima para baixo), **Rotate270** (leitura de texto de baixo para cima).</span><span class="sxs-lookup"><span data-stu-id="54a24-109">The available values for the WritingMode property are **Horizontal** (text reading left to right), **Vertical** (text reading top to bottom), **Rotate270** (text reading bottom to top).</span></span> <span data-ttu-id="54a24-110">Você deve dimensionar manualmente a largura da coluna e a altura da linha para acomodar o texto.</span><span class="sxs-lookup"><span data-stu-id="54a24-110">You must manually size the column width and the row height to accommodate the text.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-text-orientation"></a><span data-ttu-id="54a24-111">Para definir a orientação do texto</span><span class="sxs-lookup"><span data-stu-id="54a24-111">To set text orientation</span></span>  
  
1.  <span data-ttu-id="54a24-112">Crie um novo relatório ou abra um relatório existente.</span><span class="sxs-lookup"><span data-stu-id="54a24-112">Create a new report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="54a24-113">Se o painel Propriedades não estiver aberto, clique na guia **Exibir** e marque a caixa de seleção **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="54a24-113">If the Properties pane is not open, click the **View** tab and select the **Properties** check box.</span></span>  
  
3.  <span data-ttu-id="54a24-114">Clique na caixa de texto para a qual você deseja alterar a orientação do texto.</span><span class="sxs-lookup"><span data-stu-id="54a24-114">Click the text box for which you want to change text orientation.</span></span>  
  
4.  <span data-ttu-id="54a24-115">Localize a propriedade WritingMode no painel Propriedades e, na lista suspensa, selecione a orientação do texto a ser aplicada à caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="54a24-115">Locate the WritingMode property in the Properties pane and in the drop-down list select the text orientation to apply to the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="54a24-116">Quando as propriedades no painel Propriedades estiverem organizadas em categorias, WritingMode estará na categoria **Localização** .</span><span class="sxs-lookup"><span data-stu-id="54a24-116">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span>  
  
5.  <span data-ttu-id="54a24-117">Na caixa de listagem, selecione **Horizontal**, **Vertical**ou **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="54a24-117">In the list box, select **Horizontal**, **Vertical**, or **Rotate270**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54a24-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54a24-118">See Also</span></span>  
 <span data-ttu-id="54a24-119">[Caixas de texto &#40;Construtor de Relatórios e SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="54a24-119">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="54a24-120">Tutorial: Formatar texto &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="54a24-120">Tutorial: Format Text &#40;Report Builder&#41;</span></span>](../tutorial-format-text-report-builder.md)  
  
  
