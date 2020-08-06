---
title: Propriedades de configuração do SQL Server Native Client (guia Sinalizadores) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 59af121d-c8b9-4faa-91a1-b664f2c9b441
author: stevestein
ms.author: sstein
ms.openlocfilehash: b3ca7b87963fc3848bbb933a5c21f9d608d37d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582699"
---
# <a name="sql-server-native-client-configuration-properties-flags-tab"></a><span data-ttu-id="2d0a0-102">Propriedades de configuração do SQL Server Native Client (guia Sinalizadores)</span><span class="sxs-lookup"><span data-stu-id="2d0a0-102">SQL Server Native Client Configuration Properties (Flags Tab)</span></span>
  <span data-ttu-id="2d0a0-103">Os clientes do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neste computador comunicam-se com servidores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando os protocolos fornecidos no arquivo de biblioteca do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this machine, communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers using the protocols provided in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client library file.</span></span> <span data-ttu-id="2d0a0-104">Esta página fornece as configurações do computador cliente para solicitar uma conexão criptografada usando SSL.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-104">This page provides configures the client computer to request an encrypted connection using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="2d0a0-105">Se uma conexão criptografada não puder ser estabelecida, a conexão falhará.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-105">If an encrypted connection cannot be established, the connection will fail.</span></span>  
  
 <span data-ttu-id="2d0a0-106">O processo de logon sempre é criptografado.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-106">The login process is always encrypted.</span></span> <span data-ttu-id="2d0a0-107">As opções a seguir só se aplicam a dados de criptografia.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-107">The options below apply only to encrypting data.</span></span> <span data-ttu-id="2d0a0-108">Para obter mais informações sobre como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] criptografa a comunicação e obter instruções sobre como configurar o cliente para confiar na autoridade raiz do certificado do servidor, consulte "Criptografando conexões com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" e "Como habilitar conexões criptografadas no [!INCLUDE[ssDE](../../includes/ssde-md.md)] ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager)" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d0a0-108">For more information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encrypts communication and for instructions on how to configure the client to trust the root authority of the server certificate, see "Encrypting Connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" and "How to: Enable Encrypted Connections to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2d0a0-109">Opções</span><span class="sxs-lookup"><span data-stu-id="2d0a0-109">Options</span></span>  
 <span data-ttu-id="2d0a0-110">**Forçar criptografia de protocolo**</span><span class="sxs-lookup"><span data-stu-id="2d0a0-110">**Force protocol encryption**</span></span>  
 <span data-ttu-id="2d0a0-111">Solicitar uma conexão usando SSL.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-111">Request a connection using SSL.</span></span>  
  
 <span data-ttu-id="2d0a0-112">**Confiar em Certificado do Servidor**</span><span class="sxs-lookup"><span data-stu-id="2d0a0-112">**Trust Server Certificate**</span></span>  
 <span data-ttu-id="2d0a0-113">Quando definido como **Não**, o processo de cliente tenta validar o certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-113">When set to **No**, the client process attempts to validate the server certificate.</span></span> <span data-ttu-id="2d0a0-114">O cliente e o servidor devem ter um certificado emitido por uma autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-114">The client and server must have each have a certificate issues from a public certification authority.</span></span> <span data-ttu-id="2d0a0-115">Se o certificado não estiver presente no computador cliente, ou se a validação do certificado falhar, a conexão será encerrada.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-115">If the certificate is not present on the client computer, or if the validation of the certificate fails, the connection is terminated.</span></span>  
  
 <span data-ttu-id="2d0a0-116">Quando definido como **Sim**, o cliente não valida o certificado do servidor, portanto permitindo o uso de um certificado autoassinado.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-116">When set to **Yes**, the client does not validate the server certificate, thereby enabling the use of a self-signed certificate.</span></span>  
  
 <span data-ttu-id="2d0a0-117">**Confiar em Certificado do Servidor** só estará disponível se a opção **Forçar criptografia de protocolo** for definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2d0a0-117">**Trust Server Certificate** is only available if **Force protocol encryption** is set to **Yes**.</span></span>  
  
  
