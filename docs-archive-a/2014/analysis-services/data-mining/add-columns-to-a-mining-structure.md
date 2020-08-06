---
title: Adicionar colunas a uma estrutura de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- columns [data mining], mining structure columns
- adding columns
ms.assetid: 3f879344-9f66-4178-851a-e8c5ccccf4cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 093d78b36ab3aae6600b890a8137025c9dc9134e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576065"
---
# <a name="add-columns-to-a-mining-structure"></a><span data-ttu-id="fea55-102">Adicionar colunas a uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="fea55-102">Add Columns to a Mining Structure</span></span>
  <span data-ttu-id="fea55-103">Use o Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para adicionar colunas a uma estrutura de mineração depois de defini-la no Assistente de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="fea55-103">Use Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to add columns to a mining structure after you have defined it in the Data Mining Wizard.</span></span> <span data-ttu-id="fea55-104">É possível adicionar qualquer coluna existente na exibição de fonte de dados que foi usada para definir a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="fea55-104">You can add any column that exists in the data source view that was used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fea55-105">Você pode adicionar várias cópias de colunas em uma estrutura de mineração, porém deve evitar o uso de mais de uma instância da coluna dentro do mesmo modelo, a fim de impedir correlações falsas entre a coluna de origem e a coluna derivada.</span><span class="sxs-lookup"><span data-stu-id="fea55-105">You can add multiple copies of columns to a mining structure; however, you should avoid using more than one instance of the column within the same model, to avoid false correlations between the source and the derived column.</span></span>  
  
### <a name="to-add-a-column-to-a-mining-structure"></a><span data-ttu-id="fea55-106">Para adicionar uma coluna a uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="fea55-106">To add a column to a mining structure</span></span>  
  
1.  <span data-ttu-id="fea55-107">Selecione a guia **Estrutura de Mineração** no Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="fea55-107">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="fea55-108">Clique com o botão direito do mouse na estrutura de mineração e selecione **Adicionar uma Coluna**.</span><span class="sxs-lookup"><span data-stu-id="fea55-108">Right-click the mining structure and select **Add a Column**.</span></span>  
  
     <span data-ttu-id="fea55-109">A caixa de diálogo **Selecionar uma Coluna** é exibida.</span><span class="sxs-lookup"><span data-stu-id="fea55-109">The **Select a Column** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="fea55-110">Em **Tabela de Origem**, selecione a tabela na exibição de fonte de dados em que reside a coluna.</span><span class="sxs-lookup"><span data-stu-id="fea55-110">Under **Source table**, select the table in the data source view where the column resides.</span></span>  
  
4.  <span data-ttu-id="fea55-111">Em **Coluna de origem**, selecione a coluna que você quer adicionar à estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="fea55-111">Under **Source column**, select the column that you want to add to the mining structure.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="fea55-112">Se você adicionar uma coluna existente, uma cópia será incluída na estrutura, e o nome anexado com um "1".</span><span class="sxs-lookup"><span data-stu-id="fea55-112">If you add a column that already exists, a copy will be included in the structure, and the name appended with a "1".</span></span> <span data-ttu-id="fea55-113">Você pode alterar o nome da coluna copiada para algo mais descritivo digitando um novo nome na propriedade **Nome** da coluna da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="fea55-113">You can change the name of the copied column to something more descriptive by typing a new name in the **Name** property of the mining structure column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea55-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fea55-114">See Also</span></span>  
 [<span data-ttu-id="fea55-115">Tarefas e instruções da estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="fea55-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
