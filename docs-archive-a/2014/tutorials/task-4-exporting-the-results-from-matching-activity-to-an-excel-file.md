---
title: 'Tarefa 4: exportando os resultados da atividade correspondente para um arquivo do Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 644454c4-3c5a-469a-90ec-e51dc7fb99fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b583e44f887fc0595fb904ec977f1de28c2fecd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683175"
---
# <a name="task-4-exporting-the-results-from-matching-activity-to-an-excel-file"></a><span data-ttu-id="b24b4-102">Tarefa 4: Exportando os resultados da atividade de correspondência para um arquivo do Excel</span><span class="sxs-lookup"><span data-stu-id="b24b4-102">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>
  <span data-ttu-id="b24b4-103">Nesta tarefa, você exportará os resultados da atividade de correspondência para um arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="b24b4-103">In this task, you export the results from the matching activity to an Excel file.</span></span>

1.  <span data-ttu-id="b24b4-104">Na página **Exportar** , selecione **arquivo do Excel** para o **tipo de destino**.</span><span class="sxs-lookup"><span data-stu-id="b24b4-104">In the **Export** page, select **Excel File** for the **Destination Type**.</span></span>

2.  <span data-ttu-id="b24b4-105">Selecione a opção **sobrevivência Results** .</span><span class="sxs-lookup"><span data-stu-id="b24b4-105">Select **Survivorship Results** option.</span></span> <span data-ttu-id="b24b4-106">No processo sobrevivência, o DQS determina um registro sobrevivente para cada cluster com base na **regra sobrevivência** selecionada.</span><span class="sxs-lookup"><span data-stu-id="b24b4-106">In the survivorship process, DQS determines a survivor record for each cluster based on the **Survivorship Rule** you selected.</span></span>

3.  <span data-ttu-id="b24b4-107">Clique em **procurar** e navegue até a pasta onde você deseja armazenar o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="b24b4-107">Click **Browse** and navigate to the folder where you want to store the output file.</span></span>

4.  <span data-ttu-id="b24b4-108">Digite **limpo e com correspondência Suppliers.xls** para o nome e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="b24b4-108">Type **Cleansed and Matched Suppliers.xls** for the name and click **Open**.</span></span>

5.  <span data-ttu-id="b24b4-109">Confirme se o **registro dinâmico** está selecionado para a **regra sobrevivência**.</span><span class="sxs-lookup"><span data-stu-id="b24b4-109">Confirm that **Pivot Record** is selected for the **Survivorship Rule**.</span></span> <span data-ttu-id="b24b4-110">Quando você selecionar essa opção, o registro dinâmico de cada cluster será escolhido como a saída de um cluster.</span><span class="sxs-lookup"><span data-stu-id="b24b4-110">When you select this option, the pivot record for each cluster is picked for the output from a cluster.</span></span> <span data-ttu-id="b24b4-111">As outras opções para a Regra de Sobrevivência são:</span><span class="sxs-lookup"><span data-stu-id="b24b4-111">The other options for the Survivorship Rule are:</span></span>

    1.  <span data-ttu-id="b24b4-112">**Registro mais completo:** O registro sobrevivente é aquele com o maior número de campos preenchidos.</span><span class="sxs-lookup"><span data-stu-id="b24b4-112">**Most complete record:** Survivor record is the one with the largest number of populated fields.</span></span>

    2.  <span data-ttu-id="b24b4-113">**Registro mais longo:** O registro sobrevivente é aquele com o maior número de termos em campos de origem.</span><span class="sxs-lookup"><span data-stu-id="b24b4-113">**Longest record:** Survivor record is the one with the largest number of terms in source fields.</span></span>

    3.  <span data-ttu-id="b24b4-114">**Registro mais completo e mais longo:** O registro sobrevivente é aquele com o maior número de campos preenchidos e tem o maior número de termos em cada campo.</span><span class="sxs-lookup"><span data-stu-id="b24b4-114">**Most complete and longest record:** Survivor record is the one with the largest number of populated fields, and has the largest number of terms in each field.</span></span>

     <span data-ttu-id="b24b4-115">![Exportar Resultados da página correspondente](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Exportar Resultados da página correspondente")</span><span class="sxs-lookup"><span data-stu-id="b24b4-115">![Export Results from Matching Page](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Export Results from Matching Page")</span></span>

6.  <span data-ttu-id="b24b4-116">Clique em **Exportar** para exportar os resultados para um arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="b24b4-116">Click **Export** to export the results to an Excel file.</span></span>

7.  <span data-ttu-id="b24b4-117">Clique em **fechar** para fechar a caixa de diálogo **exportação de correspondência** .</span><span class="sxs-lookup"><span data-stu-id="b24b4-117">Click **Close** to close the **Matching Export** dialog box.</span></span>

8.  <span data-ttu-id="b24b4-118">Clique em **concluir** para concluir a atividade de correspondência.</span><span class="sxs-lookup"><span data-stu-id="b24b4-118">Click **Finish** to finish the matching activity.</span></span>

9. <span data-ttu-id="b24b4-119">Abra o arquivo de **Suppliers.xlsxlimpo e correspondido** e confirme se você não vê duplicatas (CódigoDoFornecedor).</span><span class="sxs-lookup"><span data-stu-id="b24b4-119">Open the **Cleansed and Matched Suppliers.xlsx** file and confirm that you do not see any duplicates (SupplierID).</span></span>

 <span data-ttu-id="b24b4-120">Agora, você tem dados de fornecedor que foram limpos e correspondidos para remover duplicatas.</span><span class="sxs-lookup"><span data-stu-id="b24b4-120">Now, you have supplier data that has been cleansed and matched to remove duplicates.</span></span>

## <a name="next-step"></a><span data-ttu-id="b24b4-121">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b24b4-121">Next Step</span></span>
 [<span data-ttu-id="b24b4-122">Lição 4: Armazenando dados do fornecedor no MDS</span><span class="sxs-lookup"><span data-stu-id="b24b4-122">Lesson 4: Storing Supplier Data in MDS</span></span>](../../2014/tutorials/lesson-4-storing-supplier-data-in-mds.md)


