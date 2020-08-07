---
title: Propriedades do SQL Server Agent (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.general.f1
ms.assetid: b51601e9-5454-43c6-bb5e-24eb2ff043c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: a67d5431be4025c18b11d6791b016fa83e957810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582254"
---
# <a name="sql-server-agent-properties-general-page"></a><span data-ttu-id="a7407-102">Propriedades do SQL Server Agent (página Geral)</span><span class="sxs-lookup"><span data-stu-id="a7407-102">SQL Server Agent Properties (General Page)</span></span>
  <span data-ttu-id="a7407-103">Use esta página para exibir e modificar as propriedades gerais do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] serviço do Agent.</span><span class="sxs-lookup"><span data-stu-id="a7407-103">Use this page to view and modify the general properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a7407-104">Opções</span><span class="sxs-lookup"><span data-stu-id="a7407-104">Options</span></span>  
 <span data-ttu-id="a7407-105">**Estado do serviço**</span><span class="sxs-lookup"><span data-stu-id="a7407-105">**Service state**</span></span>  
 <span data-ttu-id="a7407-106">Exibe o estado atual do serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a7407-106">Displays the current state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
 <span data-ttu-id="a7407-107">**Reiniciar automaticamente o SQL Server se ele parar inesperadamente**</span><span class="sxs-lookup"><span data-stu-id="a7407-107">**Auto restart SQL Server if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a7407-108">O Agent reiniciará o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] parar inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="a7407-108">Agent restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stops unexpectedly.</span></span>  
  
 <span data-ttu-id="a7407-109">**Reiniciar automaticamente o SQL Server Agent se ele parar inesperadamente**</span><span class="sxs-lookup"><span data-stu-id="a7407-109">**Auto restart SQL Server Agent if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a7407-110">reiniciará o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent parar inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="a7407-110">restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stops unexpectedly.</span></span>  
  
 <span data-ttu-id="a7407-111">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="a7407-111">**Filename**</span></span>  
 <span data-ttu-id="a7407-112">Especifica o nome do arquivo para o log de erros.</span><span class="sxs-lookup"><span data-stu-id="a7407-112">Specify the file name for the error log.</span></span>  
  
 <span data-ttu-id="a7407-113">**...**</span><span class="sxs-lookup"><span data-stu-id="a7407-113">**...**</span></span>  
 <span data-ttu-id="a7407-114">Navegue até o arquivo de log de erros.</span><span class="sxs-lookup"><span data-stu-id="a7407-114">Browse to the error log file.</span></span>  
  
 <span data-ttu-id="a7407-115">**Incluir mensagens de rastreamento de execução**</span><span class="sxs-lookup"><span data-stu-id="a7407-115">**Include execution trace messages**</span></span>  
 <span data-ttu-id="a7407-116">Inclui mensagens de rastreamento de execução no log de erros.</span><span class="sxs-lookup"><span data-stu-id="a7407-116">Includes execution trace messages in the error log.</span></span> <span data-ttu-id="a7407-117">As mensagens de rastreamento fornecem informações detalhadas sobre a operação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a7407-117">Trace messages provide detailed information on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operation.</span></span> <span data-ttu-id="a7407-118">Portanto, o arquivo de log requer mais espaço em disco quando essa opção é selecionada.</span><span class="sxs-lookup"><span data-stu-id="a7407-118">Therefore, the log file requires more disk space when this option is selected.</span></span> <span data-ttu-id="a7407-119">Essa opção só deve ser selecionada ao solucionar um problema que possa envolver o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a7407-119">This option should only be selected while troubleshooting a problem that may involve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="a7407-120">**Gravar arquivo OEM**</span><span class="sxs-lookup"><span data-stu-id="a7407-120">**Write OEM file**</span></span>  
 <span data-ttu-id="a7407-121">Grava o arquivo de log de erros como um arquivo não Unicode.</span><span class="sxs-lookup"><span data-stu-id="a7407-121">Writes the error log file as a non-Unicode file.</span></span> <span data-ttu-id="a7407-122">Isso reduz a quantidade de espaço em disco consumida pelo arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="a7407-122">This reduces the amount of disk space consumed by the log file.</span></span> <span data-ttu-id="a7407-123">Porém, mensagens que incluem dados Unicode podem ser mais difíceis de ler quando essa opção é habilitada.</span><span class="sxs-lookup"><span data-stu-id="a7407-123">However, messages that include Unicode data may be more difficult to read when this option is enabled.</span></span>  
  
 <span data-ttu-id="a7407-124">**Destinatário do net send**</span><span class="sxs-lookup"><span data-stu-id="a7407-124">**Net send recipient**</span></span>  
 <span data-ttu-id="a7407-125">Digite o nome de um operador para receber a notificação net send das mensagens que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent gravar no arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="a7407-125">Type the name of an operator to receive net send notification of messages that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent writes to the log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7407-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a7407-126">See Also</span></span>  
 <span data-ttu-id="a7407-127">[Operações](operators.md) </span><span class="sxs-lookup"><span data-stu-id="a7407-127">[Operators](operators.md) </span></span>  
 [<span data-ttu-id="a7407-128">Log de erros do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="a7407-128">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
