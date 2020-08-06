---
title: Modificar a propriedade KeyColumn de um atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- binding attributes [Analysis Services]
- attributes [Analysis Services], binding
- key columns [Analysis Services]
ms.assetid: a2643be4-8123-4cc3-baf9-e5ec54a1669d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3367a7aec84ba59efd118a56745bb76fc5266061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685362"
---
# <a name="modify-the-keycolumn-property-of-an-attribute"></a><span data-ttu-id="88745-102">Modificar a propriedade KeyColumn de um atributo</span><span class="sxs-lookup"><span data-stu-id="88745-102">Modify the KeyColumn Property of an Attribute</span></span>
  <span data-ttu-id="88745-103">Você pode modificar a propriedade **KeyColumns** de um atributo.</span><span class="sxs-lookup"><span data-stu-id="88745-103">You can modify the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="88745-104">Por exemplo, convém especificar uma chave composta em vez de uma chave única como a chave para o atributo.</span><span class="sxs-lookup"><span data-stu-id="88745-104">For example, you might want to specify a composite key instead of a single key as the key for the attribute.</span></span>  
  
### <a name="to-modify-the-keycolumns-property-of-an-attribute"></a><span data-ttu-id="88745-105">Para modificar a propriedade KeyColumn de um atributo</span><span class="sxs-lookup"><span data-stu-id="88745-105">To modify the KeyColumns property of an attribute</span></span>  
  
1.  <span data-ttu-id="88745-106">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto no qual você quer modificar a propriedade **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="88745-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project in which you want to modify the **KeyColumns** property.</span></span>  
  
2.  <span data-ttu-id="88745-107">Abra o Designer de Dimensão seguindo um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="88745-107">Open Dimension Designer by doing one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="88745-108">No **Gerenciador de Soluções**, clique com o botão direito do mouse na dimensão na pasta **Dimensões** e, em seguida, clique em **Abrir** ou **Designer de Exibição**.</span><span class="sxs-lookup"><span data-stu-id="88745-108">In **Solution Explorer**, right-click the dimension in the **Dimensions** folder, and then either click **Open** or **View Designer**.</span></span>  
  
         <span data-ttu-id="88745-109">- ou -</span><span class="sxs-lookup"><span data-stu-id="88745-109">-or-</span></span>  
  
    -   <span data-ttu-id="88745-110">No designer de cubo, na guia **estrutura do cubo** , expanda a dimensão cubo no painel **dimensões** e clique em \*\*Editar \<dimension> \*\*.</span><span class="sxs-lookup"><span data-stu-id="88745-110">In Cube Designer, on the **Cube Structure** tab, expand the cube dimension in the **Dimensions** pane and click **Edit \<dimension>**.</span></span>  
  
3.  <span data-ttu-id="88745-111">Na guia **Estrutura da Dimensão** , no painel **Atributos** , clique no atributo cuja propriedade **KeyColumns** você quer modificar.</span><span class="sxs-lookup"><span data-stu-id="88745-111">On the **Dimension Structure** tab, in the **Attributes** pane, click the attribute whose **KeyColumns** property you want to modify.</span></span>  
  
4.  <span data-ttu-id="88745-112">Na janela **Propriedades** , clique o valor da propriedade **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="88745-112">In the **Properties** window, click the value for the **KeyColumns** property.</span></span>  
  
5.  <span data-ttu-id="88745-113">Clique no botão Procurar **(...)** que aparece na célula de valor da caixa de propriedade.</span><span class="sxs-lookup"><span data-stu-id="88745-113">Click the browse **(...)** button that appears in the value cell of the property box.</span></span>  
  
     <span data-ttu-id="88745-114">A caixa de diálogo **Colunas de Chave** é aberta.</span><span class="sxs-lookup"><span data-stu-id="88745-114">The **Key Columns** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="88745-115">Para remover uma coluna de chave existente, na lista **Colunas de Chave** , selecione a coluna e, em seguida, clique no botão **\<** .</span><span class="sxs-lookup"><span data-stu-id="88745-115">To remove an existing key column, in the **Key Columns** list, select the column, and then click the **\<** button.</span></span>  
  
7.  <span data-ttu-id="88745-116">Para adicionar uma coluna de chave, na lista **Colunas Disponíveis** , selecione a coluna e clique no botão **>** .</span><span class="sxs-lookup"><span data-stu-id="88745-116">To add a key column, in the **Available Columns** list, select the column, and then click the **>** button.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="88745-117">Se você definir várias colunas de chave, a ordem de disposição das colunas na lista **Colunas de Chave** vai afetar a ordem de exibição.</span><span class="sxs-lookup"><span data-stu-id="88745-117">If you define multiple key columns, the order in which those columns appear in the **Key Columns** list affects the display order.</span></span> <span data-ttu-id="88745-118">Por exemplo, um atributo de mês tem duas colunas de chave: mês e ano.</span><span class="sxs-lookup"><span data-stu-id="88745-118">For example, a month attribute has two key columns: month and year.</span></span> <span data-ttu-id="88745-119">Se a coluna de ano aparecer na lista antes da coluna de mês, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fará a classificação por ano e, depois, por mês.</span><span class="sxs-lookup"><span data-stu-id="88745-119">If the year column appears in the list before the month column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by year and then by month.</span></span> <span data-ttu-id="88745-120">Se a coluna de mês aparecer antes da coluna de ano, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fará a classificação por mês e, depois, por ano.</span><span class="sxs-lookup"><span data-stu-id="88745-120">If the month column appears before the year column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by month and then by year.</span></span>  
  
8.  <span data-ttu-id="88745-121">Para alterar a ordem das colunas de chave, selecione uma coluna e clique no botão **Acima** ou **Abaixo** .</span><span class="sxs-lookup"><span data-stu-id="88745-121">To change the order of key columns, select a column, and then click the **Up** or **Down** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88745-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="88745-122">See Also</span></span>  
 [<span data-ttu-id="88745-123">Referência de propriedades de atributo de dimensão</span><span class="sxs-lookup"><span data-stu-id="88745-123">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
