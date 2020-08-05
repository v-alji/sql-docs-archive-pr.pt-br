---
title: Adicionar uma imagem associada a dados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df4c38d4-bfcc-41c4-aa6d-952ca6fd7a2e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ea85bdcd6eab04ff51c879a9e790b6e12f73a771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569106"
---
# <a name="add-a-data-bound-image-report-builder-and-ssrs"></a><span data-ttu-id="bb095-102">Adicionar uma imagem associada a dados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="bb095-102">Add a Data-Bound Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bb095-103">Um relatório pode incluir uma referência a uma imagem armazenada em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bb095-103">A report can include a reference to an image that is stored in a database.</span></span> <span data-ttu-id="bb095-104">Essa imagem é chamada de *imagem associada a dados*.</span><span class="sxs-lookup"><span data-stu-id="bb095-104">Such an image is known as a *data-bound image*.</span></span> <span data-ttu-id="bb095-105">As imagens exibidas ao lado dos nomes de produtos em uma lista de produtos são exemplos de imagens associadas a dados.</span><span class="sxs-lookup"><span data-stu-id="bb095-105">The pictures that appear alongside product names in a product list are examples of data-bound images.</span></span>  
  
 <span data-ttu-id="bb095-106">A adição de uma imagem associada a dados ao cabeçalho ou rodapé de uma página requer etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="bb095-106">Adding a data-bound image to a page header or page footer requires additional steps.</span></span> <span data-ttu-id="bb095-107">Para obter mais informações, consulte [Cabeçalhos e rodapés de página &#40;Construtor de Relatórios e SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bb095-107">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-data-bound-image"></a><span data-ttu-id="bb095-108">Para adicionar uma imagem associada a dados</span><span class="sxs-lookup"><span data-stu-id="bb095-108">To add a data-bound image</span></span>  
  
1.  <span data-ttu-id="bb095-109">No modo design de relatório, crie uma tabela com uma conexão da fonte de dados e um conjunto de dados com um campo que contém dados de imagem binários.</span><span class="sxs-lookup"><span data-stu-id="bb095-109">In report design view, create a table with a data source connection and a dataset with a field that contains binary image data.</span></span> <span data-ttu-id="bb095-110">Para obter mais informações, consulte [Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bb095-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="bb095-111">Insira uma coluna em sua tabela.</span><span class="sxs-lookup"><span data-stu-id="bb095-111">Insert a column in your table.</span></span> <span data-ttu-id="bb095-112">Para obter mais informações, consulte [Inserir ou excluir uma coluna &#40;Construtor de Relatórios e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bb095-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="bb095-113">No menu **Inserir** , clique em **Imagem**e na linha de dados da nova coluna.</span><span class="sxs-lookup"><span data-stu-id="bb095-113">On the **Insert** menu, click **Image**, and then click in the data row of the new column.</span></span>  
  
4.  <span data-ttu-id="bb095-114">Na página Geral da caixa de diálogo **Propriedades da Imagem** , digite um nome na caixa de texto **Nome** ou aceite o padrão.</span><span class="sxs-lookup"><span data-stu-id="bb095-114">On the General page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
5.  <span data-ttu-id="bb095-115">(Opcional) Na caixa de texto **Dica de Ferramenta** , digite o texto a ser exibido quando o usuário passar o mouse sobre a imagem no relatório renderizado para HTML.</span><span class="sxs-lookup"><span data-stu-id="bb095-115">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in the report rendered for HTML.</span></span>  
  
6.  <span data-ttu-id="bb095-116">Em **Selecione a origem da imagem**, clique em **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="bb095-116">In **Select the image source**, select **Database**.</span></span>  
  
7.  <span data-ttu-id="bb095-117">Em **Usar este Campo**, selecione o campo que contém imagens no seu relatório.</span><span class="sxs-lookup"><span data-stu-id="bb095-117">In **Use this Field**, select the field that contains images in your report.</span></span>  
  
8.  <span data-ttu-id="bb095-118">Em **Usar este tipo MIME**, selecione o tipo MIME ou o formato de arquivo da imagem; por exemplo, bmp.</span><span class="sxs-lookup"><span data-stu-id="bb095-118">In **Use this MIME type**, select the MIME type, or file format, of the image-for example, bmp.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="bb095-119">Um espaço reservado para imagem é exibido na superfície de design do relatório.</span><span class="sxs-lookup"><span data-stu-id="bb095-119">An image placeholder appears on the report design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb095-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bb095-120">See Also</span></span>  
 <span data-ttu-id="bb095-121">[Imagens &#40;Construtor de Relatórios e SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb095-121">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bb095-122">[Inserir uma imagem em um relatório &#40;Construtor de Relatórios e SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb095-122">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bb095-123">[Adicionar uma imagem externa &#40;Construtor de Relatórios e SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb095-123">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bb095-124">Caixa de diálogo Propriedades da Imagem, Geral &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bb095-124">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
