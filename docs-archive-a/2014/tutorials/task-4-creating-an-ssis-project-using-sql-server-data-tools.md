---
title: 'Tarefa 4: Criando um projeto do SSIS usando SQL Server Data Tools | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 8603ea91-2ec4-40b6-8070-4f824332f5d3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 07976dbd2c84b1385d79ce3f4ce4f616e0f706b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681287"
---
# <a name="task-4-creating-an-ssis-project-using-sql-server-data-tools"></a><span data-ttu-id="6fdc8-102">Tarefa 4: Criando um projeto SSIS usando o SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="6fdc8-102">Task 4: Creating an SSIS Project using SQL Server Data Tools</span></span>
  <span data-ttu-id="6fdc8-103">Nesta tarefa, você cria um projeto do SSIS usando **SQL Server Data Tools** para automatizar a limpeza e a correspondência de dados do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-103">In this task, you create an SSIS project by using **SQL Server Data Tools** to automate cleansing and matching supplier data.</span></span>

1.  <span data-ttu-id="6fdc8-104">Inicie o **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-104">Launch **SQL Server Data Tools**.</span></span> <span data-ttu-id="6fdc8-105">Clique em Iniciar, aponte para **todos os programas**, expanda **Microsoft SQL Server 2012**e clique em **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-105">Click Start, point to **All Programs**, expand **Microsoft SQL Server 2012**, and click **SQL Server Data Tools**.</span></span>

2.  <span data-ttu-id="6fdc8-106">No menu **Arquivo** , aponte para **Novo**e clique em **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-106">On the **File** menu, point to **New**, and click **Project**.</span></span>

3.  <span data-ttu-id="6fdc8-107">Expanda **Business Intelligence** no painel **modelos instalados** e selecione **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-107">Expand **Business Intelligence** in the **Installed Templates** pane, and select **Integration Services**.</span></span>

     <span data-ttu-id="6fdc8-108">![Visual Studio - Caixa de diálogo Novo Projeto](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - Caixa de diálogo Novo Projeto")</span><span class="sxs-lookup"><span data-stu-id="6fdc8-108">![Visual Studio - New Project Dialog Box](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - New Project Dialog Box")</span></span>

4.  <span data-ttu-id="6fdc8-109">Selecione **Integration Services projeto** na **lista de tipos de projeto**.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-109">Select **Integration Services Project** in the **list of project types**.</span></span>

5.  <span data-ttu-id="6fdc8-110">Digite **CleanseAndCurateSuppliers** para **nome** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-110">Type **CleanseAndCurateSuppliers** for **Name** and click **OK**.</span></span>

6.  <span data-ttu-id="6fdc8-111">Na janela **Gerenciador de soluções** , clique com o botão direito do mouse em **Package. dtsx** e selecione **renomear**.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-111">In **Solution Explorer** window, right-click **Package.dtsx** and select **Rename**.</span></span> <span data-ttu-id="6fdc8-112">Se você não vir **Gerenciador de soluções** janela, clique em **Exibir** na barra de menus e clique em **Gerenciador de soluções**.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-112">If you don't see **Solution Explorer** window, click **View** on the menu bar and click **Solution Explorer**.</span></span>

     <span data-ttu-id="6fdc8-113">![Package.dtsx - Menu Renomear](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Menu Renomear")</span><span class="sxs-lookup"><span data-stu-id="6fdc8-113">![Package.dtsx - Rename Menu](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Rename Menu")</span></span>

7.  <span data-ttu-id="6fdc8-114">Digite **CleanseAndCurate. dtsx** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-114">Type **CleanseAndCurate.dtsx** and press **ENTER**.</span></span> <span data-ttu-id="6fdc8-115">Certifique-se de que a **extensão** permaneça **. dtsx**.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-115">Make sure that the **extension** remains **.dtsx**.</span></span>

## <a name="next-step"></a><span data-ttu-id="6fdc8-116">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6fdc8-116">Next Step</span></span>
 [<span data-ttu-id="6fdc8-117">Tarefa 5: Adicionando a tarefa de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="6fdc8-117">Task 5: Adding Data Flow Task</span></span>](task-5-adding-data-flow-task.md)


