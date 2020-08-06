---
title: Gerar e executar o script de log suplementar | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- supLog
ms.assetid: 6e940d93-12c6-4cda-9333-5489b245f0e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1437a4b0f790376268095d8e52afa981af865b44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678930"
---
# <a name="generate-and-run-the-supplemental-logging-script"></a><span data-ttu-id="b89bf-102">Gerar e executar scripts de log suplementares</span><span class="sxs-lookup"><span data-stu-id="b89bf-102">Generate and Run the Supplemental Logging Script</span></span>
  <span data-ttu-id="b89bf-103">Use a página Configurar tabelas para capturar alterações para executar um script no banco de dados de origem Oracle que configura o registro em log suplementar.</span><span class="sxs-lookup"><span data-stu-id="b89bf-103">Use the Set up Tables for Capturing Changes page to run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
 <span data-ttu-id="b89bf-104">**Para executar os scripts suplementares de registro em log**</span><span class="sxs-lookup"><span data-stu-id="b89bf-104">**To run the supplemental logging scripts**</span></span>  
  
 <span data-ttu-id="b89bf-105">Clique em **Executar Script** para executar o script suplementar de registro em log nas tabelas definidas para a instância CDC.</span><span class="sxs-lookup"><span data-stu-id="b89bf-105">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="b89bf-106">Este script instrui o banco de dados Oracle para gravar todas as colunas de interesse em seus logs de transação ao registrar em log operações UPDATE para tabelas capturadas.</span><span class="sxs-lookup"><span data-stu-id="b89bf-106">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="b89bf-107">Este script é examinado e executado normalmente por um administrador do sistema Oracle.</span><span class="sxs-lookup"><span data-stu-id="b89bf-107">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
 <span data-ttu-id="b89bf-108">Você também pode executar os scripts manualmente usando o SQL \* Plus.</span><span class="sxs-lookup"><span data-stu-id="b89bf-108">You can also run the scripts manually using SQL \* Plus.</span></span>  
  
 <span data-ttu-id="b89bf-109">**Para executar os scripts manualmente**</span><span class="sxs-lookup"><span data-stu-id="b89bf-109">**To run the scripts manually**</span></span>  
  
 <span data-ttu-id="b89bf-110">Clique em **Copiar** para colar o script na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b89bf-110">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="b89bf-111">Abra o SQL \* Plus e vá para o diretório com seu banco de dados de origem Oracle.</span><span class="sxs-lookup"><span data-stu-id="b89bf-111">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="b89bf-112">Cole o script no SQL\*Plus para executar isto.</span><span class="sxs-lookup"><span data-stu-id="b89bf-112">Paste the script into SQL\*Plus to run it.</span></span>  
  
 <span data-ttu-id="b89bf-113">Para salvar o script de log suplementar em um arquivo de texto, clique em **Salvar como** e navegue até o local onde você deseja salvar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b89bf-113">To save the supplemental logging script in a text file, click **Save as** and browse to the location where you want to save the file.</span></span> <span data-ttu-id="b89bf-114">Dê ao arquivo um nome e clique em **Salvar** para salvar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b89bf-114">Give the file a name and click **Save** to save the file.</span></span>  
  
 <span data-ttu-id="b89bf-115">Clique em **Avançar** para [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span><span class="sxs-lookup"><span data-stu-id="b89bf-115">Click **Next** to [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b89bf-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b89bf-116">See Also</span></span>  
 <span data-ttu-id="b89bf-117">[Como criar a instância de banco de dados de alteração do SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="b89bf-117">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="b89bf-118">Examinar e gerar scripts de log suplementares</span><span class="sxs-lookup"><span data-stu-id="b89bf-118">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
