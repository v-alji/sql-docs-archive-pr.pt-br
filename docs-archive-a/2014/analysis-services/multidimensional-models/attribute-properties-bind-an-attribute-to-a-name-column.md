---
title: Associar um atributo a uma coluna de nome | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- binding attributes [Analysis Services]
- name columns [Analysis Services]
- attributes [Analysis Services], binding
ms.assetid: 467f0cf3-8691-476d-a7fb-a5df4e374eaf
author: minewiskan
ms.author: owend
ms.openlocfilehash: e25c59d34744e7a067c2b3e83d248c4674772737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582661"
---
# <a name="bind-an-attribute-to-a-name-column"></a><span data-ttu-id="3737e-102">Associar um atributo a uma coluna de nome</span><span class="sxs-lookup"><span data-stu-id="3737e-102">Bind an Attribute to a Name Column</span></span>
  <span data-ttu-id="3737e-103">Este procedimento descreve como associar um atributo manualmente a uma coluna de nome, usando o painel **Atributos** no Designer de Dimensão e usando a caixa de diálogo **Associação de Objetos** .</span><span class="sxs-lookup"><span data-stu-id="3737e-103">This procedure describes how to bind an attribute to a name column manually by using the **Attributes** pane in the Dimension Designer and by using the **Object Binding** dialog box.</span></span>  
  
### <a name="to-bind-an-attribute-to-a-name-column"></a><span data-ttu-id="3737e-104">Para associar um atributo a uma coluna de nome</span><span class="sxs-lookup"><span data-stu-id="3737e-104">To bind an attribute to a name column</span></span>  
  
1.  <span data-ttu-id="3737e-105">No Designer de Dimensão, abra a dimensão na qual você deseja criar o atributo.</span><span class="sxs-lookup"><span data-stu-id="3737e-105">In Dimension Designer, open the dimension in which you want to create the attribute.</span></span>  
  
2.  <span data-ttu-id="3737e-106">Na guia **Estrutura da Dimensão** , no painel **Atributos** , clique com o botão direito do mouse no atributo que você quer configurar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3737e-106">On the **Dimension Structure** tab, in the **Attributes** pane, right-click the attribute that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3737e-107">Na janela **Propriedades** , localize a propriedade **NameColumn** e selecione **(novo)**.</span><span class="sxs-lookup"><span data-stu-id="3737e-107">In the **Properties** window, locate the **NameColumn** property, and then select **(new)**.</span></span>  
  
4.  <span data-ttu-id="3737e-108">Na caixa de diálogo **Associação de Objeto** , para **Tipo de associação**, selecione **Associação de Coluna**.</span><span class="sxs-lookup"><span data-stu-id="3737e-108">In the **Object Binding** dialog box, for **Binding type**, select **Column binding**.</span></span>  
  
5.  <span data-ttu-id="3737e-109">Na lista **Coluna de origem** , selecione a coluna à qual o atributo será associado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3737e-109">In the **Source column** list, select the column to which the attribute will be bound, and then click **OK**.</span></span>  
  
  
