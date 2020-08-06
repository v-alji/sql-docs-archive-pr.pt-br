---
title: Usar a janela Propriedades no Management Studio
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- viewing properties
- Properties window [SQL Server Management Studio]
- complex properties [SQL Server Management Studio]
ms.assetid: 903d4aca-f57c-43d9-a893-702eceaa7004
author: rothja
ms.author: jroth
ms.openlocfilehash: 5030bf85fc87482b11e91967ff8fb1baf77a213e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582945"
---
# <a name="use-the-properties-window-in-management-studio"></a><span data-ttu-id="60419-102">Usar a janela Propriedades no Management Studio</span><span class="sxs-lookup"><span data-stu-id="60419-102">Use the Properties Window in Management Studio</span></span>
  <span data-ttu-id="60419-103">A janela Propriedades descreve o estado de um item no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], como uma conexão ou um operador de plano de execução, e informações sobre objetos de banco de dados, como tabelas, exibições e designers.</span><span class="sxs-lookup"><span data-stu-id="60419-103">The Properties window describes the state of an item in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], such as a connection or a Showplan operator, and information about database objects such as tables, views, and designers.</span></span>  
  
 <span data-ttu-id="60419-104">Você pode usar a janela Propriedades para exibir as propriedades da conexão atual.</span><span class="sxs-lookup"><span data-stu-id="60419-104">You can use the Properties window to view the properties of the current connection.</span></span> <span data-ttu-id="60419-105">Muitas propriedades são somente leitura na janela Propriedades, mas podem ser alteradas em outros lugares no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60419-105">Many properties are read-only in the Properties window but can be changed elsewhere in the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="60419-106">Por exemplo, a propriedade Database de uma consulta é somente leitura na janela Propriedades, mas pode ser alterada na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="60419-106">For example, the Database property of a query is read-only in the Properties window, but can be changed on the tool bar.</span></span>  
  
### <a name="to-view-properties-using-the-properties-window"></a><span data-ttu-id="60419-107">Para exibir propriedades usando a janela Propriedades</span><span class="sxs-lookup"><span data-stu-id="60419-107">To view properties using the Properties window</span></span>  
  
1.  <span data-ttu-id="60419-108">Se a janela Propriedades não estiver visível, clique em **Janela de Propriedades** no menu **Exibir** ou pressione F4.</span><span class="sxs-lookup"><span data-stu-id="60419-108">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="60419-109">Defina o foco no objeto que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="60419-109">Set the focus on the object that you want to view.</span></span>  
  
3.  <span data-ttu-id="60419-110">Procure uma propriedade específica na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="60419-110">Look for a specific property in the Properties window.</span></span>  
  
### <a name="to-view-connection-properties-of-a-query-window"></a><span data-ttu-id="60419-111">Para exibir propriedades de conexão de uma janela de consulta</span><span class="sxs-lookup"><span data-stu-id="60419-111">To view connection properties of a query window</span></span>  
  
1.  <span data-ttu-id="60419-112">Se a janela Propriedades não estiver visível, clique em **Janela de Propriedades** no menu **Exibir** ou pressione F4.</span><span class="sxs-lookup"><span data-stu-id="60419-112">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="60419-113">Na janela Propriedades, você pode ver todas as propriedades de conexão.</span><span class="sxs-lookup"><span data-stu-id="60419-113">In the Properties window, you can see all the connection properties.</span></span>  
  
### <a name="to-view-the-properties-of-a-showplan-operator"></a><span data-ttu-id="60419-114">Para exibir as propriedades de um operador de plano de execução</span><span class="sxs-lookup"><span data-stu-id="60419-114">To view the properties of a Showplan operator</span></span>  
  
1.  <span data-ttu-id="60419-115">No menu **Consulta** , clique em **Incluir Plano de Execução Real**.</span><span class="sxs-lookup"><span data-stu-id="60419-115">On the **Query** menu, click **Include Actual Execution Plan**.</span></span>  
  
2.  <span data-ttu-id="60419-116">No Editor de Consultas SQL, digite e execute uma consulta.</span><span class="sxs-lookup"><span data-stu-id="60419-116">In the SQL Query Editor, type and execute a query.</span></span>  
  
3.  <span data-ttu-id="60419-117">Se a janela Propriedades não estiver visível, clique em **Janela de Propriedades** no menu **Exibir** ou pressione F4.</span><span class="sxs-lookup"><span data-stu-id="60419-117">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
4.  <span data-ttu-id="60419-118">Na guia **Plano de execução** do Editor de Consultas SQL, clique nos ícones dos operadores para exibir informações sobre os operadores na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="60419-118">On the **Execution plan** tab of the SQL Query Editor click the icons of the operators to view information about the operators in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60419-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60419-119">See Also</span></span>  
 [<span data-ttu-id="60419-120">Janela Propriedades &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="60419-120">Properties Window &#40;Management Studio&#41;</span></span>](../../ssms/properties-window-management-studio.md)  
  
  
