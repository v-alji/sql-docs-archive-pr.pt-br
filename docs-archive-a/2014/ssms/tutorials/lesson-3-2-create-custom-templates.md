---
title: Criar modelos personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tql
- templates [Transact-SQL], creating
- templates [Transact-SQL]
ms.assetid: 41098e78-b482-410e-bfe8-2ac10769ac4a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 771547b9c47672d2c075b5e7215d78744fe5f18e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681317"
---
# <a name="create-custom-templates"></a><span data-ttu-id="dd7fb-102">Criar modelos personalizados</span><span class="sxs-lookup"><span data-stu-id="dd7fb-102">Create Custom Templates</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="dd7fb-103">é fornecido com modelos para várias tarefas comuns, mas o poder real dos modelos está na capacidade de criar um modelo personalizado para um script complexo que deve ser criado com frequência.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-103">comes with templates for many common tasks, but the real power of templates lies in the ability to create a custom template for a complex script that you must create frequently.</span></span> <span data-ttu-id="dd7fb-104">Nesta prática, você criará um script simples com poucos parâmetros, mas modelos também são úteis para scripts longos e repetitivos.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-104">In this practice you will create a simple script with few parameters, but templates are useful for long, repetitive scripts, too.</span></span>  
  
## <a name="using-custom-templates"></a><span data-ttu-id="dd7fb-105">Usando modelos personalizados</span><span class="sxs-lookup"><span data-stu-id="dd7fb-105">Using Custom Templates</span></span>  
  
#### <a name="to-create-a-custom-template"></a><span data-ttu-id="dd7fb-106">Para criar um modelo personalizado</span><span class="sxs-lookup"><span data-stu-id="dd7fb-106">To create a custom template</span></span>  
  
1.  <span data-ttu-id="dd7fb-107">No Gerenciador de Modelos, expanda **Modelos do SQL Server**, clique com o botão direito do mouse em **Procedimento Armazenado**, aponte para **Novo**e clique em **Pasta**.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-107">In Template Explorer, expand **SQL Server Templates**, right-click **Stored Procedure**, point to **New**, and then click **Folder**.</span></span>  
  
2.  <span data-ttu-id="dd7fb-108">Digite **Personalizado** como o nome da nova pasta de modelos e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-108">Type **Custom** as the name of your new template folder, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="dd7fb-109">Clique com o botão direito do mouse em **Personalizado**, aponte para **Novo**e clique em **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-109">Right-click **Custom**, point to **New**, and then click **Template**.</span></span>  
  
4.  <span data-ttu-id="dd7fb-110">Digite **WorkOrdersProc** como o nome do novo modelo e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-110">Type **WorkOrdersProc** as the name of your new template, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="dd7fb-111">Clique com o botão direito do mouse em **WorkOrdersProc**e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-111">Right-click **WorkOrdersProc**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="dd7fb-112">Na caixa de diálogo **Conectar ao Mecanismo de Banco de Dados** , verifique as informações da conexão e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-112">In the **Connect to Database Engine** dialog box, verify the connection information and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="dd7fb-113">No Editor de Consultas, digite o script a seguir para criar um procedimento armazenado que procura pedidos de uma peça específica, neste caso, a Lâmina.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-113">In Query Editor, type the following script to create a stored procedure that looks up orders for a particular part, in this case the Blade.</span></span> <span data-ttu-id="dd7fb-114">(Você pode copiar e colar o código da janela Tutorial.)</span><span class="sxs-lookup"><span data-stu-id="dd7fb-114">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersForBlade')  
       DROP PROCEDURE dbo.WorkOrdersForBlade;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersForBlade  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = 'Blade';  
    GO  
    ```  
  
8.  <span data-ttu-id="dd7fb-115">Pressione F5 para executar esse script, criando o procedimento **WorkOrdersForBlade** .</span><span class="sxs-lookup"><span data-stu-id="dd7fb-115">Press F5 to execute this script, creating the **WorkOrdersForBlade** procedure.</span></span>  
  
9. <span data-ttu-id="dd7fb-116">No Pesquisador de Objetos, clique com o botão direito do mouse no servidor e clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-116">In Object Explorer, right-click your server, and then click **New Query**.</span></span> <span data-ttu-id="dd7fb-117">Uma nova janela do Editor de Consultas é aberta.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-117">A new Query Editor window opens.</span></span>  
  
10. <span data-ttu-id="dd7fb-118">No Editor de Consultas, digite **EXECUTE dbo.WorkOrdersForBlade**e pressione F5 para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-118">In Query Editor, type **EXECUTE dbo.WorkOrdersForBlade**, and then press F5 to execute the query.</span></span> <span data-ttu-id="dd7fb-119">Confirme se o painel **Resultados** retorna uma lista dos pedidos de trabalho nas folhas.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-119">Confirm that the **Results** pane returns a list of work orders for blades.</span></span>  
  
11. <span data-ttu-id="dd7fb-120">Edite o script de modelo (o script na etapa 7), substituindo a folha nome do produto pelo parâmetro <strong> *<* PRODUCT_NAME</strong>, `nvarchar(50)` , <strong> *>* nome</strong>, em quatro locais.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-120">Edit the template script (the script in step 7), replacing the product name Blade with the parameter <strong>*<* product_name</strong>, `nvarchar(50)`, <strong>name*>*</strong>, in four places.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd7fb-121">Parâmetros requerem três elementos: o nome do parâmetro que você deseja substituir, o tipo de dados do parâmetro e um valor padrão do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-121">Parameters require three elements: the name of the parameter that you want to replace, the data type of the parameter, and a default value for the parameter.</span></span>  
  
12. <span data-ttu-id="dd7fb-122">Agora o script deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="dd7fb-122">Now the script should look like:</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersFor<product_name, nvarchar(50), name>')  
       DROP PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = '<product_name, nvarchar(50), name>';  
    GO  
    ```  
  
13. <span data-ttu-id="dd7fb-123">No menu **Arquivo** , clique em **Salvar WorkOrdersProc.sql** para salvar o modelo.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-123">On the **File** menu, click **Save WorkOrdersProc.sql** to save your template.</span></span>  
  
#### <a name="to-test-the-custom-template"></a><span data-ttu-id="dd7fb-124">Para testar o modelo personalizado</span><span class="sxs-lookup"><span data-stu-id="dd7fb-124">To test the custom template</span></span>  
  
1.  <span data-ttu-id="dd7fb-125">No Gerenciador de Modelos, expanda **Procedimento Armazenado**, expanda **Personalizado**e clique duas vezes em **WorkOrderProc**.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-125">In Template Explorer, expand **Stored Procedure**, expand **Custom**, and then double-click **WorkOrderProc**.</span></span>  
  
2.  <span data-ttu-id="dd7fb-126">Na caixa de diálogo **Conectar ao Mecanismo de Banco de Dados** , complete as informações de conexão e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-126">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="dd7fb-127">Uma nova janela do Editor de Consultas será aberta, exibindo o conteúdo do modelo **WorkOrderProc** .</span><span class="sxs-lookup"><span data-stu-id="dd7fb-127">A new Query Editor window opens, containing the contents of the **WorkOrderProc** template.</span></span>  
  
3.  <span data-ttu-id="dd7fb-128">No menu **Consulta** , clique em **Especificar Valores para Parâmetros de Modelo**.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-128">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="dd7fb-129">Na caixa de diálogo **Substituir parâmetros do modelo** , para o `product_name` valor, digite **freewheel** (substituindo o conteúdo padrão) e clique em **OK** para fechar a caixa de diálogo **Substituir parâmetros do modelo** e modificar o script no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-129">In the **Replace Template Parameters** dialog box, for the `product_name` value, type **FreeWheel** (overwriting the default contents), and then click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the Query Editor.</span></span>  
  
5.  <span data-ttu-id="dd7fb-130">Pressione F5 para executar a consulta, criando o procedimento.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-130">Press F5 to execute the query, creating the procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dd7fb-131">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="dd7fb-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dd7fb-132">Salvar scripts como projetos ou soluções</span><span class="sxs-lookup"><span data-stu-id="dd7fb-132">Save Scripts as Projects or Solutions</span></span>](lesson-3-3-save-scripts-as-projects-or-solutions.md)  
  
  
