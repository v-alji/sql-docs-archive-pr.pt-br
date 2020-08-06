---
title: Opções de validação de assinatura (assinaturas de mesclagem) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.mergeoptions.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: 4958c4ab-2025-42ce-b836-6fb4e9e6f24d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 458da0387dbaa1b366348c374748c42946893feb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685525"
---
# <a name="subscription-validation-options-merge-subscriptions"></a><span data-ttu-id="55cf6-102">Opções de Validação de Assinatura (assinaturas de mesclagem)</span><span class="sxs-lookup"><span data-stu-id="55cf6-102">Subscription Validation Options (Merge Subscriptions)</span></span>
  <span data-ttu-id="55cf6-103">Use a caixa de diálogo **Opções de Validação de Assinatura** para especificar se a validação deve usar somente uma contagem de linhas ou uma contagem de linhas e uma soma de verificação binária.</span><span class="sxs-lookup"><span data-stu-id="55cf6-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="55cf6-104">Opções</span><span class="sxs-lookup"><span data-stu-id="55cf6-104">Options</span></span>  
 <span data-ttu-id="55cf6-105">**Verificar as contagens de linhas somente**</span><span class="sxs-lookup"><span data-stu-id="55cf6-105">**Verify the row counts only**</span></span>  
 <span data-ttu-id="55cf6-106">Selecione para validar se a tabela no Assinante tem o mesmo número de linhas que a tabela no Publicador.</span><span class="sxs-lookup"><span data-stu-id="55cf6-106">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="55cf6-107">Esse método não valida que o conteúdo de correspondências de linhas.</span><span class="sxs-lookup"><span data-stu-id="55cf6-107">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="55cf6-108">A validação de número de linhas fornece uma abordagem superficial à validação que pode alertá-lo sobre problemas com seus dados.</span><span class="sxs-lookup"><span data-stu-id="55cf6-108">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="55cf6-109">**Verificar as contagens de linhas e comparar as somas de verificação para verificar os dados da linha**</span><span class="sxs-lookup"><span data-stu-id="55cf6-109">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="55cf6-110">Além de contar o número de linhas no Publicador e no Assinante, uma soma de verificação de todos os dados é calculada usando o algoritmo de soma de verificação binária.</span><span class="sxs-lookup"><span data-stu-id="55cf6-110">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="55cf6-111">Se a contagem de linhas falhar, a soma de verificação não será executada.</span><span class="sxs-lookup"><span data-stu-id="55cf6-111">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="55cf6-112">Esta opção não é válida para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55cf6-112">This option is not valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55cf6-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55cf6-113">See Also</span></span>  
 <span data-ttu-id="55cf6-114">[Validar dados no Assinante](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="55cf6-114">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="55cf6-115">Validar os dados replicados</span><span class="sxs-lookup"><span data-stu-id="55cf6-115">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
