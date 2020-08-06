---
title: 'Tarefa 5: exportando resultados de limpeza para um arquivo do Excel | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: eaeafd65-d0d4-4a7d-a3ad-110ef644e90b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0dbdc1bef348e03e211e4933132985ea2c089b97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581642"
---
# <a name="task-5-exporting-cleansing-results-to-an-excel-file"></a><span data-ttu-id="30c36-102">Tarefa 5: Exportando os resultados da limpeza para um arquivo do Excel</span><span class="sxs-lookup"><span data-stu-id="30c36-102">Task 5: Exporting Cleansing Results to an Excel File</span></span>
  <span data-ttu-id="30c36-103">Nesta tarefa, você exportará resultados da atividade de limpeza para um arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="30c36-103">In this task, you export results from the cleansing activity to an Excel file.</span></span> <span data-ttu-id="30c36-104">Confira o tópico [Exportar estágio](https://msdn.microsoft.com/library/hh213061.aspx#Export) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="30c36-104">See [Export Stage](https://msdn.microsoft.com/library/hh213061.aspx#Export) topic for more details.</span></span>  
  
1.  <span data-ttu-id="30c36-105">No painel direito, selecione **Excel** para o **tipo de destino**.</span><span class="sxs-lookup"><span data-stu-id="30c36-105">In the right pane, select **Excel** for the **Destination Type**.</span></span>  
  
2.  <span data-ttu-id="30c36-106">Clique em **procurar**, especifique o nome do arquivo de saída como **fornecedor limpo List.xls**e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="30c36-106">Click **Browse**, specify the output file name as **Cleansed Supplier List.xls**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="30c36-107">Selecione **dados somente** para o formato de **saída** para exportar apenas os dados limpos.</span><span class="sxs-lookup"><span data-stu-id="30c36-107">Select **Data Only** for the **Output** format to export just the cleansed data.</span></span> <span data-ttu-id="30c36-108">A segunda opção, **dados e informações de limpeza**, permitem exportar detalhes da atividade de limpeza junto com os dados limpos.</span><span class="sxs-lookup"><span data-stu-id="30c36-108">The second option, **Data and Cleansing Info**, lets you export cleansing activity details along with the cleansed data.</span></span> <span data-ttu-id="30c36-109">A opção **padronizar formato** permite aplicar qualquer formato de saída definido em um domínio aos valores desse domínio.</span><span class="sxs-lookup"><span data-stu-id="30c36-109">The **Standardize Format** option lets you apply any output formats you define on a domain to the values of that domain.</span></span> <span data-ttu-id="30c36-110">Você não definiu um formato de saída em nenhum domínio no tutorial.</span><span class="sxs-lookup"><span data-stu-id="30c36-110">You have not defined an output format on any domain in the tutorial.</span></span>  
  
     <span data-ttu-id="30c36-111">![Página Exportar Resultados da Limpeza](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Página Exportar Resultados da Limpeza")</span><span class="sxs-lookup"><span data-stu-id="30c36-111">![Export Cleansing Results Page](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Export Cleansing Results Page")</span></span>  
  
4.  <span data-ttu-id="30c36-112">Clique em **Exportar** para exportar os dados.</span><span class="sxs-lookup"><span data-stu-id="30c36-112">Click **Export** to export the data.</span></span> <span data-ttu-id="30c36-113">Não clique em **concluir** ainda.</span><span class="sxs-lookup"><span data-stu-id="30c36-113">Do not click **Finish** yet.</span></span>  
  
5.  <span data-ttu-id="30c36-114">Clique em **fechar** na caixa de diálogo **Exportar** .</span><span class="sxs-lookup"><span data-stu-id="30c36-114">Click **Close** on the **Exporting** dialog box.</span></span>  
  
6.  <span data-ttu-id="30c36-115">Clique em **concluir** para concluir a atividade.</span><span class="sxs-lookup"><span data-stu-id="30c36-115">Click **Finish** to finish the activity.</span></span> <span data-ttu-id="30c36-116">Se você se esqueceu de exportar os resultados antes de clicar em **concluir**, clique em **Abrir projeto de qualidade de dados** na página principal do cliente do **DQS**, selecione **Limpar lista de fornecedores** na lista de projetos e clique em **Avançar** na parte inferior da tela para obter o estágio de **exportação** do processo de limpeza novamente.</span><span class="sxs-lookup"><span data-stu-id="30c36-116">If you forgot to export results before clicking **Finish**, click **Open Data Quality Project** in the main page of **DQS Client**, select **Cleanse Supplier List** from the list of projects, and click **Next** at the bottom of the screen to get to the **Export** stage of cleansing process again.</span></span> <span data-ttu-id="30c36-117">Você também pode alternar para a guia **gerenciar e exibir resultados** clicando no botão **voltar** .</span><span class="sxs-lookup"><span data-stu-id="30c36-117">You can also switch to **Manage and View Results** tab by clicking **Back** button.</span></span>  
  
7.  <span data-ttu-id="30c36-118">Abra o **List.xlsdo fornecedor limpo** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="30c36-118">Open the **Cleansed Supplier List.xls** and do the following:</span></span>  
  
    1.  <span data-ttu-id="30c36-119">Verifique se não há endereços de email que terminem com adventure-work.com (sem o caractere ') procurando por adventure-work.com na planilha.</span><span class="sxs-lookup"><span data-stu-id="30c36-119">Ensure that there are no email addresses that end with adventure-work.com (without character 's') by searching for adventure-work.com in the worksheet.</span></span>  
  
    2.  <span data-ttu-id="30c36-120">Veja que não há nenhum valor **usa** na coluna **Country** .</span><span class="sxs-lookup"><span data-stu-id="30c36-120">See that there is no **USA** value in the **Country** column.</span></span>  
  
    3.  <span data-ttu-id="30c36-121">Procure **Los Angeles** e verifique se o **State** está definido como **CA**.</span><span class="sxs-lookup"><span data-stu-id="30c36-121">Search for **Los Angeles** and see that the **State** is set to **CA**.</span></span>  
  
    4.  <span data-ttu-id="30c36-122">Confirme que não há termos **co.**, **Corp.**, e **Inc.**.</span><span class="sxs-lookup"><span data-stu-id="30c36-122">Confirm that there are no terms **Co.**, **Corp.**, and **Inc.**.</span></span>  
  
    5.  <span data-ttu-id="30c36-123">Exclua a coluna **validação de endereço** da planilha e salve o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="30c36-123">Delete the **Address Validation** column from the spreadsheet and save the excel file.</span></span> <span data-ttu-id="30c36-124">Essa coluna adicional corresponde ao domínio composto Address Validation.</span><span class="sxs-lookup"><span data-stu-id="30c36-124">This additional column corresponds to the Address Validation composite domain.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="30c36-125">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="30c36-125">Next Step</span></span>  
 [<span data-ttu-id="30c36-126">Tarefa 6: Importando valores do projeto Limpar Lista de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="30c36-126">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>](../../2014/tutorials/task-6-importing-values-from-the-cleanse-supplier-list-project.md)  
  
  
