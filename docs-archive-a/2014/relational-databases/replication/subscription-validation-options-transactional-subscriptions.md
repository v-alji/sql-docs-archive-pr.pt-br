---
title: Opções de Validação de Assinatura (assinaturas transacionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.options.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: fd66ad1f-df01-4240-9e89-8f41bff12c1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 40a617dd1beff24f8f072f5d139bec7c1ca65f33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685523"
---
# <a name="subscription-validation-options-transactional-subscriptions"></a><span data-ttu-id="ddc5f-102">Opções de Validação de Assinatura (assinaturas transacionais)</span><span class="sxs-lookup"><span data-stu-id="ddc5f-102">Subscription Validation Options (Transactional Subscriptions)</span></span>
  <span data-ttu-id="ddc5f-103">Use a caixa de diálogo **Opções de validação de assinatura** para especificar se a validação deve usar apenas uma contagem de linhas ou uma contagem de linhas e uma soma de verificação binária.</span><span class="sxs-lookup"><span data-stu-id="ddc5f-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only, or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ddc5f-104">Opções</span><span class="sxs-lookup"><span data-stu-id="ddc5f-104">Options</span></span>  
 <span data-ttu-id="ddc5f-105">**Verifique se o Assinante tem o mesmo número de linhas dos dados replicados que o Publicador**</span><span class="sxs-lookup"><span data-stu-id="ddc5f-105">**Verify that the Subscriber has the same number of rows of replicated data as the Publisher**</span></span>  
 <span data-ttu-id="ddc5f-106">Selecione o tipo de validação de contagem de linhas a ser executado.</span><span class="sxs-lookup"><span data-stu-id="ddc5f-106">Select the type of row count validation to perform.</span></span> <span data-ttu-id="ddc5f-107">Para publicações Oracle, a única opção disponível é **Calcular uma contagem de linhas real consultando as tabelas diretamente**.</span><span class="sxs-lookup"><span data-stu-id="ddc5f-107">For Oracle publications, the only available option is **Compute an actual row count by querying the tables directly**.</span></span>  
  
 <span data-ttu-id="ddc5f-108">**Comparar as somas de verificação para verificar os dados da linha**</span><span class="sxs-lookup"><span data-stu-id="ddc5f-108">**Compare checksums to verify row data**</span></span>  
 <span data-ttu-id="ddc5f-109">Além de contar o número de linhas no Publicador e no Assinante, uma soma de verificação de todos os dados é calculada usando o algoritmo de soma de verificação binária.</span><span class="sxs-lookup"><span data-stu-id="ddc5f-109">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="ddc5f-110">Se a contagem de linhas falhar, a soma de verificação não será executada.</span><span class="sxs-lookup"><span data-stu-id="ddc5f-110">If the row count fails, the checksum is not performed.</span></span>  
  
 <span data-ttu-id="ddc5f-111">**Interromper o Distribution Agent após a conclusão da validação**</span><span class="sxs-lookup"><span data-stu-id="ddc5f-111">**Stop the Distribution Agent after the validation has completed**</span></span>  
 <span data-ttu-id="ddc5f-112">Por padrão, o Distribution Agent executa continuamente.</span><span class="sxs-lookup"><span data-stu-id="ddc5f-112">By default, the Distribution Agent runs continuously.</span></span> <span data-ttu-id="ddc5f-113">Selecione essa opção para interromper o agente depois que validação for executada.</span><span class="sxs-lookup"><span data-stu-id="ddc5f-113">Select this option to stop the agent after validation is performed.</span></span> <span data-ttu-id="ddc5f-114">Isso permite verificar se validação teve êxito antes de continuar replicando dados para o Assinante.</span><span class="sxs-lookup"><span data-stu-id="ddc5f-114">This allows you to check whether validation was successful before continuing to replicate data to the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddc5f-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ddc5f-115">See Also</span></span>  
 <span data-ttu-id="ddc5f-116">[Validar dados no Assinante](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="ddc5f-116">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="ddc5f-117">Validar os dados replicados</span><span class="sxs-lookup"><span data-stu-id="ddc5f-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
