---
title: Definir análise rápida | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dcd1dc09-6eaf-440b-9ce6-fef779ff794f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6ff2c6ecd536dd5ecc34dceb358ffcf578ff3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568699"
---
# <a name="set-fast-parse"></a><span data-ttu-id="ace6e-102">Definir a análise rápida</span><span class="sxs-lookup"><span data-stu-id="ace6e-102">Set Fast Parse</span></span>
  <span data-ttu-id="ace6e-103">A propriedade de análise rápida deve ser definida para cada coluna da origem ou transformação que use a análise rápida.</span><span class="sxs-lookup"><span data-stu-id="ace6e-103">The fast parse property must be set for each column of the source or transformation that uses fast parse.</span></span> <span data-ttu-id="ace6e-104">Para definir a propriedade, use o Editor avançado da fonte Flat File e da transformação de Conversão de Dados.</span><span class="sxs-lookup"><span data-stu-id="ace6e-104">To set the property, use the Advanced editor of the Flat File source and Data Conversion transformation.</span></span>  
  
### <a name="to-set-fast-parse"></a><span data-ttu-id="ace6e-105">Para definir a análise rápida</span><span class="sxs-lookup"><span data-stu-id="ace6e-105">To set fast parse</span></span>  
  
1.  <span data-ttu-id="ace6e-106">Clique com o botão direito do mouse na fonte Arquivo Simples ou na transformação de Conversão de Dados e clique em **Mostrar Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="ace6e-106">Right-click the Flat File source or Data Conversion transformation, and then click **Show Advanced Editor**.</span></span>  
  
2.  <span data-ttu-id="ace6e-107">Na caixa de diálogo **Editor Avançado** , clique na guia **Propriedades de Entrada e Saída** .</span><span class="sxs-lookup"><span data-stu-id="ace6e-107">In the **Advanced Editor** dialog box, click the **Input and Output Properties** tab.</span></span>  
  
3.  <span data-ttu-id="ace6e-108">No painel **Entradas e Saídas** , clique na coluna para a qual você quer ativar a análise rápida.</span><span class="sxs-lookup"><span data-stu-id="ace6e-108">In the **Inputs and Outputs** pane, click the column for which you want to enable fast parse.</span></span>  
  
4.  <span data-ttu-id="ace6e-109">No janela Propriedades, expanda o nó **Propriedades personalizadas** e defina a `FastParse` propriedade como `True` .</span><span class="sxs-lookup"><span data-stu-id="ace6e-109">In the Properties window, expand the **Custom Properties** node, and then set the `FastParse` property to `True`.</span></span>  
  
5.  <span data-ttu-id="ace6e-110">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ace6e-110">Click **OK**.</span></span>  
  
  
