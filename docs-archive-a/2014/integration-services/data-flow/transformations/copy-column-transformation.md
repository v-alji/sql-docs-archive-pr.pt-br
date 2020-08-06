---
title: Copiar Transformação de Coluna | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copycolumntrans.f1
helpviewer_keywords:
- columns [Integration Services], copying
- copying columns
- Copy Column transformation
ms.assetid: 1c72a313-9026-46bc-a57f-c6b3f47346f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fd2745070a92ab71e89f3bfa9edd8673b676632b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575242"
---
# <a name="copy-column-transformation"></a><span data-ttu-id="e8600-102">transformação Copiar Coluna</span><span class="sxs-lookup"><span data-stu-id="e8600-102">Copy Column Transformation</span></span>
  <span data-ttu-id="e8600-103">A transformação Copiar Coluna cria novas colunas com a cópia de colunas de entrada e a adição de novas colunas à saída da transformação.</span><span class="sxs-lookup"><span data-stu-id="e8600-103">The Copy Column transformation creates new columns by copying input columns and adding the new columns to the transformation output.</span></span> <span data-ttu-id="e8600-104">Mais tarde no fluxo de dados, transformações diferentes podem ser aplicadas às cópias da coluna.</span><span class="sxs-lookup"><span data-stu-id="e8600-104">Later in the data flow, different transformations can be applied to the column copies.</span></span> <span data-ttu-id="e8600-105">Por exemplo, você pode usar a transformação Copiar Coluna para criar uma cópia de uma coluna e, em seguida, converter os dados copiados em caracteres maiúsculos por meio da transformação Mapa de Caracteres ou aplicar agregações à coluna nova por meio da transformação Agregação.</span><span class="sxs-lookup"><span data-stu-id="e8600-105">For example, you can use the Copy Column transformation to create a copy of a column and then convert the copied data to uppercase characters by using the Character Map transformation, or apply aggregations to the new column by using the Aggregate transformation.</span></span>  
  
## <a name="configuration-of-the-copy-column-transformation"></a><span data-ttu-id="e8600-106">Configuração da transformação Copiar Coluna</span><span class="sxs-lookup"><span data-stu-id="e8600-106">Configuration of the Copy Column Transformation</span></span>  
 <span data-ttu-id="e8600-107">Configure a transformação Copiar Coluna especificando as colunas de entrada a serem copiadas.</span><span class="sxs-lookup"><span data-stu-id="e8600-107">You configure the Copy Column transformation by specifying the input columns to copy.</span></span> <span data-ttu-id="e8600-108">É possível criar várias cópias de uma coluna ou criar cópias de várias colunas em uma operação.</span><span class="sxs-lookup"><span data-stu-id="e8600-108">You can create multiple copies of a column, or create copies of multiple columns in one operation.</span></span>  
  
 <span data-ttu-id="e8600-109">Essa transformação tem uma entrada e uma saída.</span><span class="sxs-lookup"><span data-stu-id="e8600-109">This transformation has one input and one output.</span></span> <span data-ttu-id="e8600-110">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="e8600-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="e8600-111">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="e8600-111">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e8600-112">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação Copiar Coluna** , consulte [Editor de Transformação Copiar Coluna](../../copy-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e8600-112">For more information about the properties that you can set in the **Copy Column Transformation Editor** dialog box, see [Copy Column Transformation Editor](../../copy-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="e8600-113">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="e8600-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="e8600-114">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e8600-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e8600-115">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="e8600-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="e8600-116">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="e8600-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="e8600-117">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="e8600-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8600-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e8600-118">See Also</span></span>  
 <span data-ttu-id="e8600-119">[Fluxo de Dados](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="e8600-119">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="e8600-120">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="e8600-120">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
