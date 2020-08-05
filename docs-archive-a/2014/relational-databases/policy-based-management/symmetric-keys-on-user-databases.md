---
title: Chaves simétricas em bancos de dados do usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3333ab5b-2518-4753-a0a8-57df5e5af74f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ca0fb62ccb32ce244e1087281997dcd9929df89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572003"
---
# <a name="symmetric-keys-on-user-databases"></a><span data-ttu-id="e7d2f-102">Chaves simétricas em bancos de dados de usuários</span><span class="sxs-lookup"><span data-stu-id="e7d2f-102">Symmetric Keys on User Databases</span></span>
  <span data-ttu-id="e7d2f-103">Esta regra verifica se as chaves com um comprimento menor que 128 bytes não usam o algoritmo de criptografia RC2 ou RC4.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-103">This rule checks whether keys that have a length of less than 128 bytes do not use the RC2 or RC4 encryption algorithm.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="e7d2f-104">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="e7d2f-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="e7d2f-105">Use AES de 128 bits ou maior para criar chaves simétricas para criptografia de dados.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-105">Use AES 128 bit or larger to create symmetric keys for data encryption.</span></span> <span data-ttu-id="e7d2f-106">Se não houver suporte a AES no seu sistema operacional, use 3DES.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-106">If AES is not supported by your operating system, use 3DES.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="e7d2f-107">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="e7d2f-107">For More Information</span></span>  
 [<span data-ttu-id="e7d2f-108">Escolher um algoritmo de criptografia</span><span class="sxs-lookup"><span data-stu-id="e7d2f-108">Choose an Encryption Algorithm</span></span>](../security/encryption/choose-an-encryption-algorithm.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7d2f-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7d2f-109">See Also</span></span>  
 [<span data-ttu-id="e7d2f-110">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="e7d2f-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
