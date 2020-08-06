---
title: 'Tarefa 3: Criando e executando um projeto de qualidade de dados para correspondência | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6260e911-ea8b-4c69-a39d-d1bccd565a32
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 221d6d583c61ee035c20fcb63f0ed5278f2b8678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570396"
---
# <a name="task-3-creating-and-running-a-data-quality-project-for-matching"></a><span data-ttu-id="234c6-102">Tarefa 3: Criando e executando um projeto de qualidade de dados para correspondência</span><span class="sxs-lookup"><span data-stu-id="234c6-102">Task 3: Creating and Running a Data Quality Project for Matching</span></span>
  <span data-ttu-id="234c6-103">Nesta tarefa, você criará um Projeto do Data Quality para a atividade de correspondência e executará o processo de correspondência nos dados de fornecedor limpos para remover as duplicatas nos dados.</span><span class="sxs-lookup"><span data-stu-id="234c6-103">In this task, you create a Data Quality Project for the matching activity and run the matching process on cleansed supplier data to remove any duplicates in the data.</span></span>

1.  <span data-ttu-id="234c6-104">Na página principal do **cliente do DQS**, clique em **novo projeto de qualidade de dados**.</span><span class="sxs-lookup"><span data-stu-id="234c6-104">On the main page of **DQS Client**, click **New Data Quality Project**.</span></span>

2.  <span data-ttu-id="234c6-105">Digite **remover duplicatas do fornecedor** do **nome do projeto**.</span><span class="sxs-lookup"><span data-stu-id="234c6-105">Type **Remove Supplier Duplicates** from the **Name of the project**.</span></span>

3.  <span data-ttu-id="234c6-106">Selecione **fornecedores** na lista de KBS para o campo **usar base de dados de conhecimento** .</span><span class="sxs-lookup"><span data-stu-id="234c6-106">Select **Suppliers** from the list of KBs for the **Use Knowledge Base** field.</span></span> <span data-ttu-id="234c6-107">Você criou uma política de correspondência nessa base de dados de conhecimento na lição anterior.</span><span class="sxs-lookup"><span data-stu-id="234c6-107">You have created a matching policy in this knowledge base in the previous lesson.</span></span>

4.  <span data-ttu-id="234c6-108">Selecione **correspondência** na **lista de atividades** no painel inferior direito.</span><span class="sxs-lookup"><span data-stu-id="234c6-108">Select **Matching** from the **list of activities** from the bottom-right pane.</span></span>

     <span data-ttu-id="234c6-109">![Projeto de Qualidade de Novos Dados - Correspondência selecionada](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "Projeto de Qualidade de Novos Dados - Correspondência selecionada")</span><span class="sxs-lookup"><span data-stu-id="234c6-109">![New Data Quality Project - Matching Selected](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "New Data Quality Project - Matching Selected")</span></span>

5.  <span data-ttu-id="234c6-110">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="234c6-110">Click **Next**.</span></span>

6.  <span data-ttu-id="234c6-111">Na página **Mapear** , selecione **Arquivo do Excel** em **Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="234c6-111">In the **Map** page, select **Excel File** for **Data Source**.</span></span>

7.  <span data-ttu-id="234c6-112">Clique em **procurar** e selecione **fornecedor limpo List.xls**, que é o arquivo de saída da atividade de limpeza.</span><span class="sxs-lookup"><span data-stu-id="234c6-112">Click **Browse** and select **Cleansed Supplier List.xls**, which is the output file from the cleansing activity.</span></span>

8.  <span data-ttu-id="234c6-113">Mapeie a coluna de origem **CódigoDoFornecedor** para o domínio da **ID** do fornecedor, a coluna **nome do fornecedor** para **nome do fornecedor** domínio e a coluna **ContactEmailAddress** para contatar o domínio de **email** .</span><span class="sxs-lookup"><span data-stu-id="234c6-113">Map **SupplierID** source column to the **Supplier ID** domain, **Supplier Name** column to **Supplier Name** domain, and **ContactEmailAddress** column to **Contact Email** domain.</span></span>

9. <span data-ttu-id="234c6-114">Clique em **Avançar** para alternar para a página **correspondente** .</span><span class="sxs-lookup"><span data-stu-id="234c6-114">Click **Next** to switch to the **Matching** page.</span></span>

10. <span data-ttu-id="234c6-115">Clique em **Iniciar** para iniciar o processo de correspondência.</span><span class="sxs-lookup"><span data-stu-id="234c6-115">Click **Start** to start the matching process.</span></span> <span data-ttu-id="234c6-116">Você deverá visualizar resultados semelhantes aos da tarefa anterior, pois usou o mesmo arquivo de entrada para definir a política de correspondência.</span><span class="sxs-lookup"><span data-stu-id="234c6-116">You should see results similar to those from the previous task because you used the same input file for defining the matching policy.</span></span>

11. <span data-ttu-id="234c6-117">Revise todos os registros correspondentes e sua pontuação na caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="234c6-117">Review all the matched records and their matching score in the list box.</span></span> <span data-ttu-id="234c6-118">Os resultados deverão ser iguais aos exibidos na tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="234c6-118">The results should be same as the ones you saw in the previous task.</span></span> <span data-ttu-id="234c6-119">Consulte as etapas na tarefa anterior para analisar os resultados dessa atividade de correspondência.</span><span class="sxs-lookup"><span data-stu-id="234c6-119">See the steps in the previous task to analyze the results from this matching activity.</span></span>

12. <span data-ttu-id="234c6-120">Clique em **Avançar** para alternar para a página **Exportar** .</span><span class="sxs-lookup"><span data-stu-id="234c6-120">Click **Next** to switch to the **Export** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="234c6-121">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="234c6-121">Next Step</span></span>
 [<span data-ttu-id="234c6-122">Tarefa 4: Exportando os resultados da atividade de correspondência para um arquivo do Excel</span><span class="sxs-lookup"><span data-stu-id="234c6-122">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>](../../2014/tutorials/task-4-exporting-the-results-from-matching-activity-to-an-excel-file.md)


