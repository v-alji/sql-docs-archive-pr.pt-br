---
title: Definir opções de criptografia em servidores de destino | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, encryption
- target servers [SQL Server], encryption
- multiserver environments [SQL Server], setting encryption options on target servers
ms.assetid: 1a9fd539-e166-4ea8-9f21-ac400ca74dee
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd10d2e05e59015542f41cc123de993e6128f9f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582266"
---
# <a name="set-encryption-options-on-target-servers"></a><span data-ttu-id="8384a-102">Definir opções de criptografia em servidores de destino</span><span class="sxs-lookup"><span data-stu-id="8384a-102">Set Encryption Options on Target Servers</span></span>
  <span data-ttu-id="8384a-103">Se você não puder usar um certificado para comunicações criptografadas em SSL (Secure Sockets Layer) entre os servidores mestres e parte ou todos os servidores de destino, mas quiser criptografar o canal entre eles, configure o servidor de destino para que use o nível de segurança necessário.</span><span class="sxs-lookup"><span data-stu-id="8384a-103">If you cannot use a certificate for Secure Sockets Layer (SSL) encrypted communications between master servers and some or all of your target servers, but you want to encrypt the channel between them, configure the target server to use the level of security required.</span></span>  
  
 <span data-ttu-id="8384a-104">Para configurar o nível apropriado de segurança necessário para um canal de comunicação do servidor mestre/servidor de destino específico, defina a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subchave do registro do agente \*\* \\ \ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server\*\* \<*instance_name*> **\SQLServerAgent\MsxEncryptChannelOptions (REG_DWORD)** no servidor de destino como um dos valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="8384a-104">To configure the appropriate level of security required for a specific master server/target server communication channel, set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\**\<*instance_name*>**\SQLServerAgent\MsxEncryptChannelOptions(REG_DWORD)** on the target server to one of the following values.</span></span> <span data-ttu-id="8384a-105">O valor de \<*instance_name*> é **MSSQL.** _n_.</span><span class="sxs-lookup"><span data-stu-id="8384a-105">The value of \<*instance_name*> is **MSSQL.**_n_.</span></span> <span data-ttu-id="8384a-106">Por exemplo, **MSSQL.1** ou **MSSQL.3**.</span><span class="sxs-lookup"><span data-stu-id="8384a-106">For example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
|<span data-ttu-id="8384a-107">Valor</span><span class="sxs-lookup"><span data-stu-id="8384a-107">Value</span></span>|<span data-ttu-id="8384a-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="8384a-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8384a-109">**0**</span><span class="sxs-lookup"><span data-stu-id="8384a-109">**0**</span></span>|<span data-ttu-id="8384a-110">Desabilita a criptografia entre este servidor de destino e o servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="8384a-110">Disables encryption between this target server and the master server.</span></span> <span data-ttu-id="8384a-111">Escolha esta opção apenas quando o canal entre o servidor de destino e servidor mestre estiver protegido por outros meios.</span><span class="sxs-lookup"><span data-stu-id="8384a-111">Choose this option only when the channel between the target server and master server is secured by another means.</span></span>|  
|<span data-ttu-id="8384a-112">**1**</span><span class="sxs-lookup"><span data-stu-id="8384a-112">**1**</span></span>|<span data-ttu-id="8384a-113">Habilita criptografia apenas entre este servidor de destino e o servidor mestre, mas nenhuma validação de certificado é necessária.</span><span class="sxs-lookup"><span data-stu-id="8384a-113">Enables encryption only between this target server and the master server, but no certificate validation is required.</span></span>|  
|<span data-ttu-id="8384a-114">**2**</span><span class="sxs-lookup"><span data-stu-id="8384a-114">**2**</span></span>|<span data-ttu-id="8384a-115">Habilita criptografia SSL completa e validação de certificado entre este servidor de destino e o servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="8384a-115">Enables full SSL encryption and certificate validation between this target server and the master server.</span></span> <span data-ttu-id="8384a-116">Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="8384a-116">This setting is the default.</span></span> <span data-ttu-id="8384a-117">A menos que haja um motivo específico para escolher um valor diferente, nós recomendamos não alterá-la.</span><span class="sxs-lookup"><span data-stu-id="8384a-117">Unless you have specific reason to choose a different value, we recommend not changing it.</span></span>|  
  
 <span data-ttu-id="8384a-118">Se **1** ou **2** for especificado, SSL deverá estar habilitado em ambos os servidores, mestre e de destino.</span><span class="sxs-lookup"><span data-stu-id="8384a-118">If **1** or **2** is specified, you must have SSL enabled on both the master and target servers.</span></span> <span data-ttu-id="8384a-119">Se **2** for especificado, também será necessário haver um certificado apropriadamente assinado no servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="8384a-119">If **2** is specified, you must also have a properly signed certificate present on the master server.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8384a-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8384a-120">See Also</span></span>  
 [<span data-ttu-id="8384a-121">Habilitar conexões criptografadas no Mecanismo de Banco de Dados &#40;SQL Server Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="8384a-121">Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;</span></span>](../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md)  
  
  
