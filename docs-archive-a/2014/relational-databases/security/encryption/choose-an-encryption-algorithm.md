---
title: Escolha um algoritmo de criptografia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], algorithms
- encryption [SQL Server], algorithms
- security [SQL Server], encryption
- algorithms [SQL Server encryption]
ms.assetid: 8227028c-a9c9-489d-bd27-fbf8242634ae
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b2c5292b4a00a3ad81e53fdbc603bb584130613
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685507"
---
# <a name="choose-an-encryption-algorithm"></a><span data-ttu-id="b1b14-102">Escolher um algoritmo de criptografia</span><span class="sxs-lookup"><span data-stu-id="b1b14-102">Choose an Encryption Algorithm</span></span>
  <span data-ttu-id="b1b14-103">A criptografia é um dos muitos recursos de proteção que estão disponíveis para o administrador que deseja oferecer segurança a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1b14-103">Encryption is one of several defenses-in-depth that are available to the administrator who wants to secure an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b1b14-104">Os algoritmos de criptografia definem as transformações de dados que não podem ser facilmente revertidas por usuários não autorizados.</span><span class="sxs-lookup"><span data-stu-id="b1b14-104">Encryption algorithms define data transformations that cannot be easily reversed by unauthorized users.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="b1b14-105">permite que administradores e desenvolvedores escolham entre diversos algoritmos, incluindo DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, RC4 de 128 bits, DESX, AES de 128 bits, AES de 192 bits e AES de 256 bits.</span><span class="sxs-lookup"><span data-stu-id="b1b14-105">allows administrators and developers to choose from among several algorithms, including DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, 128-bit RC4, DESX, 128-bit AES, 192-bit AES, and 256-bit AES.</span></span>  
  
 <span data-ttu-id="b1b14-106">Nenhum algoritmo é ideal para todas as situações e informações sobre o benefício de cada um está além do escopo dos Manuais Online do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b1b14-106">No single algorithm is ideal for all situations, and guidance on the merits of each is beyond the scope of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="b1b14-107">Porém, os seguintes princípios gerais se aplicam:</span><span class="sxs-lookup"><span data-stu-id="b1b14-107">However, the following general principles apply:</span></span>  
  
-   <span data-ttu-id="b1b14-108">A criptografia segura geralmente consome mais recursos da CPU que criptografia menos segura.</span><span class="sxs-lookup"><span data-stu-id="b1b14-108">Strong encryption generally consumes more CPU resources than weak encryption.</span></span>  
  
-   <span data-ttu-id="b1b14-109">As chaves extensas geralmente produzem uma criptografia mais segura que as chaves mais curtas.</span><span class="sxs-lookup"><span data-stu-id="b1b14-109">Long keys generally yield stronger encryption than short keys.</span></span>  
  
-   <span data-ttu-id="b1b14-110">A criptografia assimétrica é mais fraca que a criptografia simétrica, que usa o mesmo comprimento de chave mas é relativamente lenta.</span><span class="sxs-lookup"><span data-stu-id="b1b14-110">Asymmetric encryption is weaker than symmetric encryption using the same key length, but it is relatively slow.</span></span>  
  
-   <span data-ttu-id="b1b14-111">Codificações em bloco com chaves extensas são mais seguras que codificações em fluxo.</span><span class="sxs-lookup"><span data-stu-id="b1b14-111">Block ciphers with long keys are stronger than stream ciphers.</span></span>  
  
-   <span data-ttu-id="b1b14-112">Senhas longas e complexas são mais seguras que senhas curtas.</span><span class="sxs-lookup"><span data-stu-id="b1b14-112">Long, complex passwords are stronger than short passwords.</span></span>  
  
-   <span data-ttu-id="b1b14-113">Se você estiver criptografando muitos dados, deve criptografá-los usando uma chave simétrica e criptografar a chave simétrica com uma chave assimétrica.</span><span class="sxs-lookup"><span data-stu-id="b1b14-113">If you are encrypting lots of data, you should encrypt the data using a symmetric key, and encrypt the symmetric key with an asymmetric key.</span></span>  
  
-   <span data-ttu-id="b1b14-114">Dados criptografados não podem ser compactados, mas dados compactados podem ser criptografados.</span><span class="sxs-lookup"><span data-stu-id="b1b14-114">Encrypted data cannot be compressed, but compressed data can be encrypted.</span></span> <span data-ttu-id="b1b14-115">Se você usar compactação, deverá compactar os dados antes de criptografá-los.</span><span class="sxs-lookup"><span data-stu-id="b1b14-115">If you use compression, you should compress data before encrypting it.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b1b14-116">O algoritmo RC4 tem suporte somente para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="b1b14-116">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="b1b14-117">O novo material só pode ser criptografado por meio do algoritmo RC4 ou RC4_128 quando o banco de dados está no nível de compatibilidade 90 ou 100.</span><span class="sxs-lookup"><span data-stu-id="b1b14-117">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="b1b14-118">(Não recomendável.) Use um algoritmo mais recente; por exemplo, um dos algoritmos AES.</span><span class="sxs-lookup"><span data-stu-id="b1b14-118">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="b1b14-119">No [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] e versões posteriores, o material criptografado por meio do algoritmo RC4 ou RC4_128 pode ser descriptografado em qualquer nível de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="b1b14-119">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] and higher material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
>   
>  <span data-ttu-id="b1b14-120">O uso repetido do mesmo RC4 ou RC4_128 KEY_GUID em blocos de dados diferentes resulta na mesma chave RC4 porque o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não fornece um salt automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b1b14-120">Repeated use of the same RC4 or RC4_128 KEY_GUID on different blocks of data will result in the same RC4 key because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not provide a salt automatically.</span></span> <span data-ttu-id="b1b14-121">O uso da mesma chave RC4 repetidamente é um erro bem conhecido que resulta em criptografia muito fraca.</span><span class="sxs-lookup"><span data-stu-id="b1b14-121">Using the same RC4 key repeatedly is a well-known error that will result in very weak encryption.</span></span> <span data-ttu-id="b1b14-122">Portanto, preterimos as palavras-chave RC4 e RC4_128.</span><span class="sxs-lookup"><span data-stu-id="b1b14-122">Therefore, we have deprecated the RC4 and RC4_128 keywords.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="b1b14-123">Para obter mais informações sobre os algoritmos de criptografia e sobre a tecnologia de criptografia, consulte [Conceitos de segurança de chave](https://go.microsoft.com/fwlink/?LinkId=62082) no Guia do desenvolvedor do .NET Framework do MSDN.</span><span class="sxs-lookup"><span data-stu-id="b1b14-123">For more information about encryption algorithms and encryption technology, see [Key Security Concepts](https://go.microsoft.com/fwlink/?LinkId=62082) in the .NET Framework Developer's Guide on MSDN.</span></span>  
  
 <span data-ttu-id="b1b14-124">**Esclarecimento em relação aos algoritmos DES:**</span><span class="sxs-lookup"><span data-stu-id="b1b14-124">**Clarification regarding DES algorithms:**</span></span>  
  
-   <span data-ttu-id="b1b14-125">O DESX foi nomeado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="b1b14-125">DESX was incorrectly named.</span></span> <span data-ttu-id="b1b14-126">As chaves simétricas criadas com ALGORITHM = DESX na verdade usam a cifra TRIPLE DES com uma chave de 192 bits.</span><span class="sxs-lookup"><span data-stu-id="b1b14-126">Symmetric keys created with ALGORITHM = DESX actually use the TRIPLE DES cipher with a 192-bit key.</span></span> <span data-ttu-id="b1b14-127">O algoritmo DESX não é fornecido.</span><span class="sxs-lookup"><span data-stu-id="b1b14-127">The DESX algorithm is not provided.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
-   <span data-ttu-id="b1b14-128">As chaves simétricas criadas com ALGORITHM = TRIPLE_DES_3KEY usam TRIPLE DES com uma chave de 192 bits.</span><span class="sxs-lookup"><span data-stu-id="b1b14-128">Symmetric keys created with ALGORITHM = TRIPLE_DES_3KEY use TRIPLE DES with a 192-bit key.</span></span>  
  
-   <span data-ttu-id="b1b14-129">As chaves simétricas criadas com ALGORITHM = TRIPLE_DES usam TRIPLE DES com uma chave de 128 bits.</span><span class="sxs-lookup"><span data-stu-id="b1b14-129">Symmetric keys created with ALGORITHM = TRIPLE_DES use TRIPLE DES with a 128-bit key.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b1b14-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="b1b14-130">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1b14-131">Criptografando com o uso de uma chave simétrica.</span><span class="sxs-lookup"><span data-stu-id="b1b14-131">Encrypting using a symmetric key.</span></span>|[<span data-ttu-id="b1b14-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1b14-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)|  
|<span data-ttu-id="b1b14-133">Criptografando com o uso de uma chave assimétrica.</span><span class="sxs-lookup"><span data-stu-id="b1b14-133">Encrypting using an asymmetric key.</span></span>|[<span data-ttu-id="b1b14-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1b14-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)|  
|<span data-ttu-id="b1b14-135">Criptografando com o uso de um certificado.</span><span class="sxs-lookup"><span data-stu-id="b1b14-135">Encrypting using a certificate.</span></span>|[<span data-ttu-id="b1b14-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1b14-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)|  
|<span data-ttu-id="b1b14-137">Criptografando arquivos de banco de dados com o uso de criptografia transparente de dados.</span><span class="sxs-lookup"><span data-stu-id="b1b14-137">Encrypting database files using transparent data encryption.</span></span>|[<span data-ttu-id="b1b14-138">TDE &#40;Transparent Data Encryption&#41;</span><span class="sxs-lookup"><span data-stu-id="b1b14-138">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)|  
|<span data-ttu-id="b1b14-139">Como criptografar uma coluna de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="b1b14-139">How to encrypt one column of a table.</span></span>|[<span data-ttu-id="b1b14-140">Criptografar uma coluna de dados</span><span class="sxs-lookup"><span data-stu-id="b1b14-140">Encrypt a Column of Data</span></span>](encrypt-a-column-of-data.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b1b14-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b1b14-141">See Also</span></span>  
 <span data-ttu-id="b1b14-142">[Criptografia do SQL Server](sql-server-encryption.md) </span><span class="sxs-lookup"><span data-stu-id="b1b14-142">[SQL Server Encryption](sql-server-encryption.md) </span></span>  
 [<span data-ttu-id="b1b14-143">Hierarquia de criptografia</span><span class="sxs-lookup"><span data-stu-id="b1b14-143">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
