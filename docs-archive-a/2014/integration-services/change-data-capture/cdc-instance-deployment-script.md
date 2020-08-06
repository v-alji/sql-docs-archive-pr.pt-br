---
title: Script de implantação de instância CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fa82822-ac99-48ef-a18d-f4f3a77105b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6deea884168c2329e312eeaa2be16c28a955cca3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685245"
---
# <a name="cdc-instance-deployment-script"></a><span data-ttu-id="364e9-102">Script de implantação de instância CDC</span><span class="sxs-lookup"><span data-stu-id="364e9-102">CDC Instance Deployment Script</span></span>
  <span data-ttu-id="364e9-103">A caixa de diálogo CDC Instance Deployment Script que exibe o script de implantação de instância CDC.</span><span class="sxs-lookup"><span data-stu-id="364e9-103">The CDC Instance Deployment Script dialog box that displays the CDC instance deployment script.</span></span> <span data-ttu-id="364e9-104">Este script pode ser usado para recriar o banco de dados CDC com todos os seus artefatos em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diferente.</span><span class="sxs-lookup"><span data-stu-id="364e9-104">This script can be used to re-create the CDC database with all of its artifacts on a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="364e9-105">Depois de concluído o script de implantação, você deve ter certeza do seguinte:</span><span class="sxs-lookup"><span data-stu-id="364e9-105">At the completion of the deployment script, you should make sure of the following:</span></span>  
  
-   <span data-ttu-id="364e9-106">O script de implantação presume que a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino estivesse preparada para o Oracle CDC, usando o Console de Configuração do Serviço Oracle CDC ou usando **prepare script** que o programa cria.</span><span class="sxs-lookup"><span data-stu-id="364e9-106">The deployment script assumes that the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance was prepared for Oracle CDC, by using the Oracle CDC Service Configuration Console or by using **prepare script** that program creates.</span></span>  
  
-   <span data-ttu-id="364e9-107">A parte do script que é usada para habilitar o banco de dados para CDC precisa ser executada por um `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="364e9-107">The part of the script that is used to enable the database for CDC needs to be run by a `sysadmin`.</span></span>  
  
-   <span data-ttu-id="364e9-108">O script não preserva a senha da mineração de logs do Oracle.</span><span class="sxs-lookup"><span data-stu-id="364e9-108">The script does not preserve the Oracle log-mining password.</span></span> <span data-ttu-id="364e9-109">Isto precisa ser definido manualmente depois que o script é executado e o Serviço Oracle CDC é iniciado.</span><span class="sxs-lookup"><span data-stu-id="364e9-109">This needs to be set manually after the script is run and the Oracle CDC Service is started.</span></span>  
  
 <span data-ttu-id="364e9-110">Selecione as seguintes opções na caixa de diálogo **CDC Instance Deployment Script** .</span><span class="sxs-lookup"><span data-stu-id="364e9-110">Select the following options in the **CDC Instance Deployment Script** dialog box.</span></span>  
  
 <span data-ttu-id="364e9-111">**Salvar como**</span><span class="sxs-lookup"><span data-stu-id="364e9-111">**Save As**</span></span>  
 <span data-ttu-id="364e9-112">Salva o script em um arquivo de texto que você pode salvar em qualquer local desejado.</span><span class="sxs-lookup"><span data-stu-id="364e9-112">Saves the script in a text file that you can save in any location you want.</span></span> <span data-ttu-id="364e9-113">Você pode copiar o arquivo com o script para qualquer outro servidor executá-lo lá.</span><span class="sxs-lookup"><span data-stu-id="364e9-113">You can copy the file with the script to any other server to run it there.</span></span>  
  
 <span data-ttu-id="364e9-114">**Copy**</span><span class="sxs-lookup"><span data-stu-id="364e9-114">**Copy**</span></span>  
 <span data-ttu-id="364e9-115">Copiar o script para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="364e9-115">Copies the script to the clipboard.</span></span> <span data-ttu-id="364e9-116">Você pode em seguida colar o script no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou em qualquer editor de texto para executar os scripts posteriormente.</span><span class="sxs-lookup"><span data-stu-id="364e9-116">You can then paste the script into the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor to run the scripts later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="364e9-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="364e9-117">See Also</span></span>  
 [<span data-ttu-id="364e9-118">Preparar o SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="364e9-118">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
