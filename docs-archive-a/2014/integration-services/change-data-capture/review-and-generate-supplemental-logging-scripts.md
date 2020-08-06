---
title: Examinar e gerar scripts de log suplementares | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- scripts
ms.assetid: 5c858ae2-37d6-42e8-a252-7f6ed4e628a7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb735c0ee318ac68d48c71c09fc76ec305eb2552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572140"
---
# <a name="review-and-generate-supplemental-logging-scripts"></a><span data-ttu-id="f1b58-102">Revisar e gerar scripts de log suplementares</span><span class="sxs-lookup"><span data-stu-id="f1b58-102">Review and Generate Supplemental Logging Scripts</span></span>
  <span data-ttu-id="f1b58-103">Use a guia **Scripts** para executar ou executar novamente um script no banco de dados de origem Oracle que configura o registro em log suplementar.</span><span class="sxs-lookup"><span data-stu-id="f1b58-103">Use the **Scripts** tab to run or re-run a script on the Oracle source database that sets up supplemental logging.</span></span>  
  
 <span data-ttu-id="f1b58-104">Antes de executar os scripts, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f1b58-104">Before you run the scripts select one of the following:</span></span>  
  
 <span data-ttu-id="f1b58-105">**Inclua alterações nesta sessão**</span><span class="sxs-lookup"><span data-stu-id="f1b58-105">**Include changes in this session**</span></span>  
 <span data-ttu-id="f1b58-106">Selecione isto para executar o script em qualquer nova tabela que foi adicionada à instância CDC ou em tabelas que foram alteradas de alguma maneira usando o editor de Propriedades.</span><span class="sxs-lookup"><span data-stu-id="f1b58-106">Select this to run the script on any new table that was added to the CDC instance or on tables that were changed in any way using the Properties editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1b58-107">Se nenhuma alteração foi feita às tabelas na instância CDC, a área de script suplementar de registro em log do Oracle estará vazia.</span><span class="sxs-lookup"><span data-stu-id="f1b58-107">If no changes were made to the tables in the CDC instance, the Oracle supplemental logging script area will be empty.</span></span>  
  
 <span data-ttu-id="f1b58-108">**Inclua todas as instâncias de tabelas/captura**</span><span class="sxs-lookup"><span data-stu-id="f1b58-108">**Include all tables/capture instances**</span></span>  
 <span data-ttu-id="f1b58-109">Selecione isto para executar o script em todas as tabelas e instâncias de captura na instância CDC.</span><span class="sxs-lookup"><span data-stu-id="f1b58-109">Select this to run the script on all of the tables and capture instances in the CDC instance.</span></span>  
  
 <span data-ttu-id="f1b58-110">Depois de selecionar uma destas opções, execute o script suplementar de registro em log.</span><span class="sxs-lookup"><span data-stu-id="f1b58-110">After you select one of these options, run the supplemental logging script.</span></span>  
  
### <a name="to-run-the-supplemental-logging-scripts"></a><span data-ttu-id="f1b58-111">Para executar os scripts suplementares de registro em log</span><span class="sxs-lookup"><span data-stu-id="f1b58-111">To run the supplemental logging scripts</span></span>  
  
1.  <span data-ttu-id="f1b58-112">Clique em **Executar Script** para executar o script suplementar de registro em log nas tabelas definidas para a instância CDC.</span><span class="sxs-lookup"><span data-stu-id="f1b58-112">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="f1b58-113">Este script instrui o banco de dados Oracle para gravar todas as colunas de interesse em seus logs de transação ao registrar em log operações UPDATE para tabelas capturadas.</span><span class="sxs-lookup"><span data-stu-id="f1b58-113">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="f1b58-114">Este script é examinado e executado normalmente por um administrador do sistema Oracle.</span><span class="sxs-lookup"><span data-stu-id="f1b58-114">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
2.  <span data-ttu-id="f1b58-115">Quando você executa os scripts de log suplementares, a caixa de diálogo Oracle Credentials for Running Script abre e você fornece um nome de usuário e senha do Oracle válidos.</span><span class="sxs-lookup"><span data-stu-id="f1b58-115">When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="f1b58-116">Para obter informações sobre como fornecer as credenciais corretas do Oracle, consulte [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="f1b58-116">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
 <span data-ttu-id="f1b58-117">Você também pode executar os scripts manualmente usando o SQL \* Plus, se necessário.</span><span class="sxs-lookup"><span data-stu-id="f1b58-117">You can also run the scripts manually using SQL \* Plus, if necessary.</span></span>  
  
### <a name="to-run-the-scripts-manually"></a><span data-ttu-id="f1b58-118">Para executar os scripts manualmente</span><span class="sxs-lookup"><span data-stu-id="f1b58-118">To run the scripts manually</span></span>  
  
1.  <span data-ttu-id="f1b58-119">Clique em **Copiar** para colar o script na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="f1b58-119">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="f1b58-120">Abra o SQL \* Plus e vá para o diretório com seu banco de dados de origem Oracle.</span><span class="sxs-lookup"><span data-stu-id="f1b58-120">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="f1b58-121">Cole o script no SQL\*Plus para executar isto.</span><span class="sxs-lookup"><span data-stu-id="f1b58-121">Paste the script into SQL\*Plus to run it.</span></span>  
  
### <a name="to-save-the-supplemental-logging-script-in-a-text-file"></a><span data-ttu-id="f1b58-122">Para salvar o script suplementar de registro em log em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="f1b58-122">To save the supplemental logging script in a text file</span></span>  
  
1.  <span data-ttu-id="f1b58-123">Clique em **Salvar como** e navegue até o local em que você deseja salvar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="f1b58-123">Click **Save as** and browse to the location where you want to save the file.</span></span>  
  
2.  <span data-ttu-id="f1b58-124">Dê ao arquivo um nome e clique em **Salvar** para salvar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="f1b58-124">Give the file a name and click **Save** to save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b58-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1b58-125">See Also</span></span>  
 <span data-ttu-id="f1b58-126">[Como editar as propriedades de instância CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f1b58-126">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="f1b58-127">Credenciais Oracle para executar scripts</span><span class="sxs-lookup"><span data-stu-id="f1b58-127">Oracle Credentials for Running Script</span></span>](oracle-credentials-for-running-script.md)  
  
  
