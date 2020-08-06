---
title: 'Tarefa 3: importando valores de domínio de um arquivo do Excel | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 242e8309-1195-495b-9cd5-aa127748c185
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 707a3925bb6d0014e2a1248f904123b076024e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570394"
---
# <a name="task-3-importing-domain-values-from-an-excel-file"></a><span data-ttu-id="948a6-102">Tarefa 3: Importando valores de domínio de um arquivo do Excel</span><span class="sxs-lookup"><span data-stu-id="948a6-102">Task 3: Importing Domain Values from an Excel File</span></span>

  <span data-ttu-id="948a6-103">Nesta tarefa, você importará valores para o domínio **State** de uma planilha de um arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="948a6-103">In this task, you import values for the **State** domain from a worksheet of an Excel file.</span></span>

1.  <span data-ttu-id="948a6-104">Clique no domínio **State** na **Lista de domínios**.</span><span class="sxs-lookup"><span data-stu-id="948a6-104">Click **State** domain in the **Domain list**.</span></span>

2.  <span data-ttu-id="948a6-105">Verifique se a guia **Valores de Domínio** está ativa no painel direito.</span><span class="sxs-lookup"><span data-stu-id="948a6-105">Ensure that the **Domain Values** tab is active in the right pane.</span></span>

3.  <span data-ttu-id="948a6-106">No painel direito, na barra de ferramentas, clique na **seta para baixo** ao lado do botão **Importar valores** e clique em **Importar Valores Válidos do Excel**.</span><span class="sxs-lookup"><span data-stu-id="948a6-106">In the right pane, from the toolbar, click **down arrow** next to the **Import Values** button, and click **Import Valid Values from Excel**.</span></span>

     <span data-ttu-id="948a6-107">![Importar Valores Válidos do Menu Excel](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Importar Valores Válidos do Menu Excel")</span><span class="sxs-lookup"><span data-stu-id="948a6-107">![Import Valid Values from Excel Menu](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Import Valid Values from Excel Menu")</span></span>

4.  <span data-ttu-id="948a6-108">Clique em **Procurar**, selecione **Suppliers.xls**e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="948a6-108">Click **Browse**, select **Suppliers.xls**, and click **Open**.</span></span>

5.  <span data-ttu-id="948a6-109">Selecione **StatesToImport$** em **Planilha**.</span><span class="sxs-lookup"><span data-stu-id="948a6-109">Select **StatesToImport$** for the **Worksheet**.</span></span>

     <span data-ttu-id="948a6-110">![Caixa de diálogo Importar Valores do Domínio](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Caixa de diálogo Importar Valores do Domínio")</span><span class="sxs-lookup"><span data-stu-id="948a6-110">![Import Domain Values Dialog Box](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Import Domain Values Dialog Box")</span></span>

6.  <span data-ttu-id="948a6-111">Clique em **OK** para fechar a caixa de diálogo **Importar Valores de Domínio** .</span><span class="sxs-lookup"><span data-stu-id="948a6-111">Click **OK** to close the **Import Domain Values** dialog box.</span></span> <span data-ttu-id="948a6-112">Você deve visualizar todos os nomes dos estados que importou na lista.</span><span class="sxs-lookup"><span data-stu-id="948a6-112">You should see all the names of states you imported in the list.</span></span> <span data-ttu-id="948a6-113">Observe que a opção **Mostrar Somente Novo** é selecionada automaticamente após a importação.</span><span class="sxs-lookup"><span data-stu-id="948a6-113">Notice that **Show Only New** option is automatically selected after importing.</span></span> <span data-ttu-id="948a6-114">Quando você importa valores e não vê os valores antigos na lista, isso ocorre porque essa opção é habilitada automaticamente após a importação.</span><span class="sxs-lookup"><span data-stu-id="948a6-114">When you import values and you don't see the old values in the list, it is because this option is automatically enabled after importing.</span></span> <span data-ttu-id="948a6-115">Para visualizar todos os valores, desmarque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="948a6-115">To see all the values, clear the check box.</span></span> <span data-ttu-id="948a6-116">Se você importar o mesmo conjunto de valores novamente, nenhum dos valores será importado, pois já existem no domínio.</span><span class="sxs-lookup"><span data-stu-id="948a6-116">If you import the same set of values again, none of the values are imported as they already exist in the domain.</span></span>

     <span data-ttu-id="948a6-117">![Caixa de seleção Mostrar Somente Novos em Valores do Domínio](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Caixa de seleção Mostrar Somente Novos em Valores do Domínio")</span><span class="sxs-lookup"><span data-stu-id="948a6-117">![Show Only New Checkbox on Domain Values](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Show Only New Checkbox on Domain Values")</span></span>

## <a name="next-step"></a><span data-ttu-id="948a6-118">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="948a6-118">Next Step</span></span>
 [<span data-ttu-id="948a6-119">Tarefa 4: Definindo regras de domínio</span><span class="sxs-lookup"><span data-stu-id="948a6-119">Task 4: Setting Domain Rules</span></span>](../../2014/tutorials/task-4-setting-domain-rules.md)


