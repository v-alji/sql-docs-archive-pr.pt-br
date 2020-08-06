---
title: Implementar uma política de assinatura definindo um valor de registro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- signing policies [Integration Services]
ms.assetid: 64f6966f-2292-401f-acb1-2ccb5aee484a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e844b65df5b45f212554f7583f4e4b327b740e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570126"
---
# <a name="implement-a-signing-policy-by-setting-a-registry-value"></a><span data-ttu-id="f565c-102">Implementar uma política de assinatura por meio da configuração de um valor do Registro</span><span class="sxs-lookup"><span data-stu-id="f565c-102">Implement a Signing Policy by Setting a Registry Value</span></span>
  <span data-ttu-id="f565c-103">Você pode usar um valor opcional do Registro para gerenciar uma política da organização para carregar pacotes assinados ou não assinados.</span><span class="sxs-lookup"><span data-stu-id="f565c-103">You can use an optional registry value to manage an organization's policy for loading signed or unsigned packages.</span></span> <span data-ttu-id="f565c-104">Se você usar o valor do Registro, será preciso criar esse valor em cada computador em que os pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] serão executados e no qual deseja aplicar a política.</span><span class="sxs-lookup"><span data-stu-id="f565c-104">If you use this registry value, you must create this registry value on each computer on which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages will run and on which you want to enforce the policy.</span></span> <span data-ttu-id="f565c-105">Depois que o valor do Registro tiver sido definido, o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] verificará as assinaturas antes de carregar pacotes.</span><span class="sxs-lookup"><span data-stu-id="f565c-105">After the registry value has been set, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] will check or verify the signatures before loading packages.</span></span>  
  
 <span data-ttu-id="f565c-106">O procedimento deste tópico descreve como adicionar o valor opcional DWORD de `BlockedSignatureStates` para a chave do Registro HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span><span class="sxs-lookup"><span data-stu-id="f565c-106">This procedure in this topic describes how to add the optional `BlockedSignatureStates` DWORD value to the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS registry key.</span></span> <span data-ttu-id="f565c-107">Os valores de dados no `BlockedSignatureStates` determinam se um pacote deve ser bloqueado se possuir uma assinatura não confiável, uma assinatura inválida ou não esteja assinado.</span><span class="sxs-lookup"><span data-stu-id="f565c-107">The data value in `BlockedSignatureStates` determines whether a package should be blocked if it has an untrusted signature, has an invalid signature, or is unsigned.</span></span> <span data-ttu-id="f565c-108">Com relação ao status das assinaturas usadas para assinar os pacotes, o valor do Registro `BlockedSignatureStates` usa as seguintes definições:</span><span class="sxs-lookup"><span data-stu-id="f565c-108">With regard to the status of signatures used to sign packages, the `BlockedSignatureStates` registry value uses the following definitions:</span></span>  
  
-   <span data-ttu-id="f565c-109">Uma *assinatura válida* é aquela que pode ser lida com êxito.</span><span class="sxs-lookup"><span data-stu-id="f565c-109">A *valid signature* is one that can be read successfully.</span></span>  
  
-   <span data-ttu-id="f565c-110">Uma *assinatura inválida* é aquela em que a soma de verificação descriptografada (o hash unidirecional do código de pacote criptografado por uma chave privada) não corresponde à soma de verificação descriptografada calculada como parte do processo de carregamento de pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f565c-110">An *invalid signature* is one for which the decrypted checksum (the one-way hash of the package code encrypted by a private key) does not match the decrypted checksum that is calculated as part of the process of loading [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
-   <span data-ttu-id="f565c-111">Uma *assinatura confiável* é aquela criada usando um certificado digital assinado por uma Autoridade de Certificação Raiz Confiável.</span><span class="sxs-lookup"><span data-stu-id="f565c-111">A *trusted signature* is one that is created by using a digital certificate signed by a Trusted Root Certification Authority.</span></span> <span data-ttu-id="f565c-112">Essa configuração não exige que o signatário esteja na lista do usuário de Fornecedores Confiáveis.</span><span class="sxs-lookup"><span data-stu-id="f565c-112">This setting does not require the signer to be found in the user's list of Trusted Publishers.</span></span>  
  
-   <span data-ttu-id="f565c-113">Uma *assinatura não confiável* é aquela que não é possível verificar se foi emitida por uma Autoridade de Certificação Raiz Confiável ou é uma assinatura que não é atual.</span><span class="sxs-lookup"><span data-stu-id="f565c-113">An *untrusted signature* is one that cannot be verified as issued by a Trusted Root Certification Authority, or a signature that is not current.</span></span>  
  
 <span data-ttu-id="f565c-114">A tabela a seguir lista os valores válidos dos dados de DWORD e sua política associada.</span><span class="sxs-lookup"><span data-stu-id="f565c-114">The following table lists the valid values of the DWORD data and their associated policy.</span></span>  
  
|<span data-ttu-id="f565c-115">Valor</span><span class="sxs-lookup"><span data-stu-id="f565c-115">Value</span></span>|<span data-ttu-id="f565c-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="f565c-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f565c-117">0</span><span class="sxs-lookup"><span data-stu-id="f565c-117">0</span></span>|<span data-ttu-id="f565c-118">Nenhuma restrição administrativa.</span><span class="sxs-lookup"><span data-stu-id="f565c-118">No administrative restriction.</span></span>|  
|<span data-ttu-id="f565c-119">1</span><span class="sxs-lookup"><span data-stu-id="f565c-119">1</span></span>|<span data-ttu-id="f565c-120">Bloquear assinaturas inválidas.</span><span class="sxs-lookup"><span data-stu-id="f565c-120">Block invalid signatures.</span></span><br /><br /> <span data-ttu-id="f565c-121">Essa configuração não bloqueia pacotes não assinados.</span><span class="sxs-lookup"><span data-stu-id="f565c-121">This setting does not block unsigned packages.</span></span>|  
|<span data-ttu-id="f565c-122">2</span><span class="sxs-lookup"><span data-stu-id="f565c-122">2</span></span>|<span data-ttu-id="f565c-123">Bloquear assinaturas inválidas e não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="f565c-123">Block invalid and untrusted signatures.</span></span><br /><br /> <span data-ttu-id="f565c-124">Essa configuração não bloqueia pacotes não assinados, mas bloqueia assinaturas geradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f565c-124">This setting does not block unsigned packages, but blocks self-generated signatures.</span></span>|  
|<span data-ttu-id="f565c-125">3</span><span class="sxs-lookup"><span data-stu-id="f565c-125">3</span></span>|<span data-ttu-id="f565c-126">Bloquear assinaturas inválidas e não confiáveis e pacotes não assinados</span><span class="sxs-lookup"><span data-stu-id="f565c-126">Block invalid and untrusted signatures and unsigned packages</span></span><br /><br /> <span data-ttu-id="f565c-127">Essa configuração também bloqueia assinaturas geradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f565c-127">This setting also blocks self-generated signatures.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f565c-128">A configuração recomendada para é `BlockedSignatureStates` é 3.</span><span class="sxs-lookup"><span data-stu-id="f565c-128">The recommended setting for `BlockedSignatureStates` is 3.</span></span> <span data-ttu-id="f565c-129">Essa configuração fornece maior proteção contra pacotes não assinados ou assinaturas que não são válidas nem confiáveis.</span><span class="sxs-lookup"><span data-stu-id="f565c-129">This setting provides the greatest protection against unsigned packages or signatures that are either not valid or untrusted.</span></span> <span data-ttu-id="f565c-130">Porém, a configuração recomendada talvez não seja apropriada em todas as circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="f565c-130">However, the recommended setting may not be appropriate in all circumstances.</span></span> <span data-ttu-id="f565c-131">Para obter mais informações sobre como assinar ativos digitais, consulte o tópico "[Introdução à assinatura de código](https://go.microsoft.com/fwlink/?LinkId=51414)", na biblioteca do MSDN.</span><span class="sxs-lookup"><span data-stu-id="f565c-131">For more information about signing digital assets, see the topic, "[Introduction to Code Signing](https://go.microsoft.com/fwlink/?LinkId=51414)," in the MSDN Library.</span></span>  
  
### <a name="to-implement-a-signing-policy-for-packages"></a><span data-ttu-id="f565c-132">Para implementar uma política de assinatura para pacotes</span><span class="sxs-lookup"><span data-stu-id="f565c-132">To implement a signing policy for packages</span></span>  
  
1.  <span data-ttu-id="f565c-133">No menu **Iniciar** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f565c-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="f565c-134">Na caixa de diálogo Executar, digite `Regedit` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f565c-134">In the Run dialog box, type `Regedit`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="f565c-135">Localize a chave do Registro, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span><span class="sxs-lookup"><span data-stu-id="f565c-135">Locate the registry key, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span></span>  
  
4.  <span data-ttu-id="f565c-136">Clique com o botão direito do mouse em **MSDTS**, aponte para **Novo**e clique em **Valor DWORD**.</span><span class="sxs-lookup"><span data-stu-id="f565c-136">Right-click **MSDTS**, point to **New**, and then click **DWORD Value**.</span></span>  
  
5.  <span data-ttu-id="f565c-137">Atualize o nome do valor novo para `BlockedSignatureStates`.</span><span class="sxs-lookup"><span data-stu-id="f565c-137">Update the name of the new value to `BlockedSignatureStates`.</span></span>  
  
6.  <span data-ttu-id="f565c-138">Clique com o botão direito do mouse `BlockedSignatureStates` e clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="f565c-138">Right-click `BlockedSignatureStates` and click **Modify**.</span></span>  
  
7.  <span data-ttu-id="f565c-139">Na caixa de diálogo **Editar valor DWORD** , digite o valor 0, 1, 2 ou 3.</span><span class="sxs-lookup"><span data-stu-id="f565c-139">In the **Edit DWORD Value** dialog box, type the value 0, 1, 2, or 3.</span></span>  
  
8.  <span data-ttu-id="f565c-140">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f565c-140">Click **OK**.</span></span>  
  
9. <span data-ttu-id="f565c-141">No menu **Arquivo** , clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="f565c-141">On the **File** menu, click **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f565c-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f565c-142">See Also</span></span>  
 <span data-ttu-id="f565c-143">[Visão geral de segurança &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="f565c-143">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="f565c-144">Identificar a origem dos pacotes com assinaturas digitais</span><span class="sxs-lookup"><span data-stu-id="f565c-144">Identify the Source of Packages with Digital Signatures</span></span>](security/identify-the-source-of-packages-with-digital-signatures.md)  
  
  
