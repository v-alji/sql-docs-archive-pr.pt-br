---
title: Representação de partição (tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: b606cd63-755c-4ac0-b19b-95b5363afbdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6a29f273a584f3e60c6cf6458751965158cf8704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684364"
---
# <a name="partition-representation-tabular"></a><span data-ttu-id="2e626-102">Representação de partição (tabular)</span><span class="sxs-lookup"><span data-stu-id="2e626-102">Partition Representation (Tabular)</span></span>
  <span data-ttu-id="2e626-103">Para fins operacionais, uma tabela pode ser dividida em subconjuntos diferentes de linhas que, quando combinados formam a tabela; cada um desses subconjuntos é uma partição da tabela.</span><span class="sxs-lookup"><span data-stu-id="2e626-103">For operational purposes, a table can be divided in different subsets of rows that when combined together form the table; each of those subsets is a partition of the table.</span></span>  
  
## <a name="partition-representation"></a><span data-ttu-id="2e626-104">Representação de partição</span><span class="sxs-lookup"><span data-stu-id="2e626-104">Partition Representation</span></span>  
 <span data-ttu-id="2e626-105">Em termos de objetos AMO, uma representação de partição tem uma relação de mapeamento de um para um com <xref:Microsoft.AnalysisServices.Partition> e nenhum outro objeto AMO principal é necessário.</span><span class="sxs-lookup"><span data-stu-id="2e626-105">In terms of AMO objects a partition representation has a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Partition> and no other main AMO objects are required</span></span>  
  
### <a name="partition-in-amo"></a><span data-ttu-id="2e626-106">Partição no AMO</span><span class="sxs-lookup"><span data-stu-id="2e626-106">Partition in AMO</span></span>  
 <span data-ttu-id="2e626-107">Ao usar o AMO para gerenciar uma partição, você precisa localizar o grupo de medidas que representa a tabela de Modelo de tabela e trabalhar a partir daí.</span><span class="sxs-lookup"><span data-stu-id="2e626-107">When using AMO to manage a partition in a you need to find the measure group that represents the Tabular Model table and work from there.</span></span>  
  
 <span data-ttu-id="2e626-108">O snippet de código a seguir mostra como adicionar uma partição a uma tabela de modelo de tabela existente.</span><span class="sxs-lookup"><span data-stu-id="2e626-108">The following code snippet shows how to add a partition to an existing tabular model table.</span></span>  
  
```  
  
private void AddPartition(  
                     AMO.Cube modelCube  
                  ,  AMO.DataSource newDatasource  
                  ,  string mgName  
                  ,  string newPartitionName  
                  , string partitionSelectStatement  
                  , Boolean processPartition  
             )  
{  
    mgName = mgName.Trim();  
    newPartitionName = newPartitionName.Trim();  
    partitionSelectStatement = partitionSelectStatement.Trim();  
    //Validate Input  
    if (string.IsNullOrEmpty(newPartitionName) || string.IsNullOrWhiteSpace(newPartitionName))  
    {  
        MessageBox.Show(String.Format("Partition Name cannot be empty or blank"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (modelCube.MeasureGroups[mgName].Partitions.ContainsName(newPartitionName))  
    {  
        MessageBox.Show(String.Format("Partition Name already defined. Duplicated names are not allowed"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (string.IsNullOrEmpty(partitionSelectStatement) || string.IsNullOrWhiteSpace(partitionSelectStatement))  
    {  
        MessageBox.Show(String.Format("Select statement cannot be empty or blank"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    //Input validated  
    string partitionID = newPartitionName; //Using partition name as the ID  
    AMO.Partition currentPartition = new AMO.Partition(partitionID, partitionID);  
    currentPartition.StorageMode = AMO.StorageMode.InMemory;  
    currentPartition.ProcessingMode = AMO.ProcessingMode.Regular;  
    currentPartition.Source = new AMO.QueryBinding(newDatasource.ID, partitionSelectStatement);  
    modelCube.MeasureGroups[mgName].Partitions.Add(currentPartition);  
    try  
    {  
        modelCube.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
        if (processPartition)  
        {  
            modelCube.MeasureGroups[mgName].Partitions[partitionID].Process(AMO.ProcessType.ProcessFull);  
            MessageBox.Show(String.Format("Partition successfully processed."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
        }  
  
    }  
    catch (AMO.AmoException amoXp)  
    {  
        MessageBox.Show(String.Format("AMO exception accessing the server.\nError message: {0}", amoXp.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
    }  
    catch (Exception)  
    {  
        throw;  
    }  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="2e626-109">Exemplo de AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="2e626-109">AMO2Tabular sample</span></span>  
 <span data-ttu-id="2e626-110">No entanto, para compreender como usar o AMO para criar e manipular representações de partição, consulte o código-fonte do exemplo AMO para Tabela.</span><span class="sxs-lookup"><span data-stu-id="2e626-110">However, to have an understanding on how to use AMO to create and manipulate partition representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="2e626-111">O exemplo está disponível no Codeplex.</span><span class="sxs-lookup"><span data-stu-id="2e626-111">The sample is available at Codeplex.</span></span> <span data-ttu-id="2e626-112">Uma nota importante sobre o código: o código é fornecido apenas como um suporte aos conceitos lógicos explicados aqui; ele não deve ser usado em um ambiente de produção, nem para fins que não sejam pedagógicos.</span><span class="sxs-lookup"><span data-stu-id="2e626-112">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
