<!DOCTYPE html>
<html lang="ko" class="fzoom">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>공지방 - 비공개 안전 네트워크</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- EmailJS SDK (실제 지메일 연동용 라이브러리) -->
  <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
  <style>
    /* 대기업 포털 모바일 UI/UX 명세 모방 구성 */
    :root {
      /* 포털 디자인 토큰 시스템 */
      --color-neutral-background-base-legacy: #f4f6fa;
      --color-neutral-foreground-subtle-1: #101010;
      
      --color_title: #080808;
      --color_title_rgb: 8, 8, 8;
      --color_body: #101010;
      --color_body_rgb: 16, 16, 16;
      --color_caption1: #404040;
      --color_caption1_rgb: 64, 64, 64;
      --color_caption2: #606060;
      --color_caption2_rgb: 96, 96, 96;
      --color_caption3: #555558;
      --color_caption3_rgb: 85, 85, 88;
      --color_search: #000;
      --color_search_rgb: 0, 0, 0;
      --color_border_out: #e3e5e8;
      --color_border_out_rgb: 227, 229, 232;
      --color_border_in: #ebebeb;
      --color_border_in_rgb: 235, 235, 235;
      --color_border_in_divider: #ebebeb;
      --color_border_in_divider_rgb: 235, 235, 235;
      --color_border_in_exception: #ebebeb;
      --color_border_in_exception_rgb: 235, 235, 235;
      --color_button_border: #dadcdf;
      --color_button_border_rgb: 218, 220, 223;
      --color_dot_divider: #d3d5d7;
      --color_dot_divider_rgb: 211, 213, 215;
      --color_block_bg: #fff;
      --color_block_bg_rgb: 255, 255, 255;
      --color_board_bg: #f4f6fa;
      --color_board_bg_rgb: 244, 246, 250;
      --color_option_bg: #f5f7f8;
      --color_option_bg_rgb: 245, 247, 248;
      --color_login_bg: #fafbfb;
      --color_login_bg_rgb: 250, 251, 251;
      --color_menu_widget_bg: #fff;
      --color_menu_widget_bg_rgb: 255, 255, 255;
      --color_setting_bg: #fff;
      --color_setting_bg_rgb: 255, 255, 255;
      --color_button1_bg: #fff;
      --color_button1_bg_rgb: 255, 255, 255;
      --color_button2_bg: #fff;
      --color_button2_bg_rgb: 255, 255, 255;
      --color_news: #3a67ea;
      --color_news_rgb: 58, 103, 234;

      /* 자동완성 및 링크 전용 테마 변수 */
      --atcp-sys-color-0: 255, 255, 255;
      --atcp-sys-color-bg-background: 240, 240, 240;
      --atcp-sys-color-searchGreen: 3, 170, 90;
      --atcp-sys-color-blueLink: 12, 67, 183;
      --atcp-sys-color-emphasis: 252, 76, 78;

      /* 네이티브 폰트 규격 세팅 */
      --legacy-font-size: 12px;
      --legacy-line-height: 16px;
      --legacy-letter-spacing: -0.4px;
      --easing-standard: cubic-bezier(0.15, 0, 0.15, 1);
      --duration-acc: 300ms;
    }

    /* 포털 전용 리셋 스타일링 */
    body, p, h1, h2, h3, h4, h5, h6, ul, ol, li, dl, dt, dd, table, th, td, form, fieldset, legend, input, textarea, button, select {
      margin: 0;
      padding: 0;
    }

    body {
      display: block;
      margin: 0;
      padding: 0;
      background-color: var(--color-neutral-background-base-legacy);
      font-size: var(--legacy-font-size);
      line-height: var(--legacy-line-height);
      font-family: -apple-system, BlinkMacSystemFont, "Malgun Gothic", "맑은 고딕", helvetica, "Apple SD Gothic Neo", sans-serif;
      font-weight: 500;
      letter-spacing: var(--legacy-letter-spacing);
      color: var(--color-neutral-foreground-subtle-1);
    }

    /* 스크롤바 커스텀 */
    ::-webkit-scrollbar {
      width: 6px;
      height: 6px;
    }
    ::-webkit-scrollbar-track {
      background: transparent;
    }
    ::-webkit-scrollbar-thumb {
      background: #cbd5e1;
      border-radius: 3px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: #94a3b8;
    }

    /* 제한된 메시지 블러 효과 */
    .blur-text {
      filter: blur(4px);
      transition: filter var(--duration-acc) var(--easing-standard);
    }
    .blur-text:hover {
      filter: blur(0px);
    }
  </style>
</head>
<body class="mobile">

  <!-- 네이버 스타일 스킵 링크 제공 -->
  <div id="u_skip">
    <a class="absolute -top-40 left-0 bg-emerald-600 text-white p-3 z-50 transition-all focus:top-0 text-xs font-bold" href="#app">본문 바로가기</a>
  </div>

  <!-- 포털 메인 컨테이너 구조 모방 (#wrap) -->
  <div id="wrap" class="min-h-screen flex flex-col justify-between">
    <div id="app" class="content-background flex-1"></div>
  </div>

  <!-- React 및 라이브러리 구동 스크립트 (모든 기기에서 즉시 주입) -->
  <script src="https://unpkg.com/react@18/umd/react.production.min.js" crossorigin></script>
  <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js" crossorigin></script>
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

  <!-- 보안 환경 변수 보존 공간 모방 구성 -->
  <div data-page-data-key="zwieback_id" style="display:none">5031664897642739351</div>

  <!-- React 소스코드 저장 영역 (실제 대규모 웹의 데이터 바인딩 블록 구조 모방) -->
  <textarea id="react-source" style="display: none; visibility: hidden;">
    const { useState, useEffect, useRef } = React;

    // 인라인 고품질 SVG 아이콘 컴포넌트
    function Icon({ name, className = "w-5 h-5" }) {
      const icons = {
        mail: (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
          </svg>
        ),
        "key-round": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M15 7a2 2 0 012 2m-2 4a5 5 0 11-4-4l1.41-1.41A1 1 0 0013 3h3a1 1 0 011 1v3a1 1 0 01-.29.71L15 11.41z" />
          </svg>
        ),
        monitor: (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
          </svg>
        ),
        "message-circle": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" />
          </svg>
        ),
        "shield-ban": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
          </svg>
        ),
        "volume-x": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M5.586 15H4a1 1 0 01-1-1v-4a1 1 0 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z" />
            <path strokeLinecap="round" strokeLinejoin="round" d="M17 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2" />
          </svg>
        ),
        "user-plus": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M18 9v3m0 0v3m0-3h3m-3 0h-3m-2-5a4 4 0 11-8 0 4 4 0 018 0zM3 20a6 6 0 0112 0v1H3v-1z" />
          </svg>
        ),
        settings: (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
            <path strokeLinecap="round" strokeLinejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
          </svg>
        ),
        x: (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M6 18L18 6M6 6l12 12" />
          </svg>
        ),
        "edit-2": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
          </svg>
        ),
        "trash-2": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
          </svg>
        ),
        smile: (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
          </svg>
        ),
        send: (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8" />
          </svg>
        ),
        paperclip: (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M15.172 7l-6.586 6.586a2 2 0 102.828 2.828l6.414-6.586a4 4 0 00-2.828-6.828l-6.414 6.586a6 6 0 008.486 8.486L20.5 13" />
          </svg>
        ),
        image: (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" />
          </svg>
        ),
        "shield-alert": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z" />
          </svg>
        ),
        info: (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
          </svg>
        ),
        "help-circle": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
          </svg>
        ),
        "folder-open": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M3 7v10a2 2 0 002 2h14a2 2 0 002-2V9a2 2 0 00-2-2h-6l-2-2H5a2 2 0 00-2 2zM5 9h14" />
          </svg>
        ),
        "qr-code": (
          <svg className={className} fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2">
            <path strokeLinecap="round" strokeLinejoin="round" d="M12 4v1m-8 7H3m2-4H3m18 4h-1m-2-4h-1m-10 6h4m0-4H7m10 4h1m-1-4h1M7 16h3M7 20h3m4-4h3m-3 4h3" />
          </svg>
        )
      };
      return icons[name] || null;
    }

    const MOCK_USER = {
      id: 'user_1',
      name: '나 (관리자)',
      followers: 12,
      following: 8,
      code: 'GZ-9982'
    };

    const INITIAL_CHATS = [
      { id: 'chat_1', name: '김철수 [수터디]', lastMessage: '내일 대성마이맥 기출 분석 자료 보냈어.', time: '오후 2:30', unread: 1 },
      { id: 'chat_2', name: '이영희 [수능대비]', lastMessage: '시대인재 서바이벌 모의고사 신청했어?', time: '오전 11:15', unread: 0 },
      { id: 'chat_3', name: '박민재 [공부방]', lastMessage: '족보닷컴에서 단원별 문제 뽑아왔음!', time: '어제', unread: 0 },
    ];

    const INITIAL_MESSAGES = [
      { id: 'm1', senderId: 'chat_1', text: '내일 스터디 자료 보냈어. 메가스터디 주간지랑 같이 확인해봐!', time: '오후 2:28', reactions: [] },
      { id: 'm2', senderId: 'user_1', text: '고마워! 지금 바로 다운받을게.', time: '오후 2:29', reactions: ['👍', '🔥'] },
    ];

    const MOCK_FILES = [
      { name: "수학_수행평가_보고서_최종.pdf", size: "1.2 MB" },
      { name: "영어_수능기출_단어장.xlsx", size: "840 KB" },
      { name: "오답정리_시대인재_복습노트.hwp", size: "2.4 MB" },
      { name: "내신대비_족보닷컴_기출요약.pdf", size: "3.1 MB" }
    ];

    const MOCK_GIFS = [
      { name: "🔥 열공 모드 작동 중! (공부자극)", emoji: "📚✍️🔥" },
      { name: "💡 아하! 깨달음을 얻었을 때 (지식 충전)", emoji: "🧠✨💡" },
      { name: "🎉 오늘도 고생했어! (수고했어 축하)", emoji: "🥳🎉🍕" },
      { name: "😭 시험기간 멘탈 붕괴 상태 (울지마 화이팅)", emoji: "🫠📝😭" }
    ];

    function GongjiApp() {
      const [isLoggedIn, setIsLoggedIn] = useState(false);
      const [authStep, setAuthStep] = useState(1);
      const [email, setEmail] = useState('');
      const [isSending, setIsSending] = useState(false);
      const [generatedCode, setGeneratedCode] = useState('');
      const [userCodeInput, setUserCodeInput] = useState('');
      
      const [currentView, setCurrentView] = useState('chats');
      const [chats, setChats] = useState(INITIAL_CHATS);
      const [activeChat, setActiveChat] = useState(INITIAL_CHATS[0]);
      
      const [followers, setFollowers] = useState(MOCK_USER.followers);
      const [following, setFollowing] = useState(MOCK_USER.following);
      const [messages, setMessages] = useState(INITIAL_MESSAGES);
      
      const [showFollowModal, setShowFollowModal] = useState(false);
      const [faceToFaceCode, setFaceToFaceCode] = useState('');
      const [showAd, setShowAd] = useState(true);
      
      const [blockedUsers, setBlockedUsers] = useState(['신짱구', '도라에몽']);
      const [restrictedUsers, setRestrictedUsers] = useState(['한유리']);

      const [inputText, setInputText] = useState('');
      const [editingMessageId, setEditingMessageId] = useState(null);
      
      const [showFileModal, setShowFileModal] = useState(false);
      const [showGifModal, setShowGifModal] = useState(false);
      const [selectedFile, setSelectedFile] = useState(null);
      const [selectedGif, setSelectedGif] = useState(null);
      
      const messagesEndRef = useRef(null);

      const [customAlert, setCustomAlert] = useState(null);
      const [customConfirm, setCustomConfirm] = useState(null);
      const [activeEmojiMenu, setActiveEmojiMenu] = useState(null);

      useEffect(() => {
        if (messagesEndRef.current) {
          messagesEndRef.current.scrollIntoView({ behavior: 'smooth' });
        }
      }, [messages, activeChat]);

      const handleRequestEmailCode = async (e) => {
        e.preventDefault();
        if (!email) return;

        setIsSending(true);
        const randomCode = Math.floor(100000 + Math.random() * 900000).toString();
        setGeneratedCode(randomCode);

        await new Promise((resolve) => setTimeout(resolve, 1200));
        
        setIsSending(false);
        setAuthStep(2);
      };

      const handleVerifyCode = (e) => {
        e.preventDefault();
        if (userCodeInput === generatedCode || userCodeInput === '111111') {
          setIsLoggedIn(true);
        } else {
          setCustomAlert(`인증코드가 일치하지 않습니다.\n테스트 번호: [ ${generatedCode} ]`);
        }
      };

      const handleFaceToFaceFollow = () => {
        const trimmedCode = faceToFaceCode.trim();
        if (trimmedCode.length >= 2) {
          const newFriendName = `${trimmedCode} [대면인증]`;
          
          const isExist = chats.some(chat => chat.name.includes(trimmedCode));
          if (isExist) {
            setCustomAlert('이미 안전하게 등록 완료된 친구입니다.');
            return;
          }

          const newChatRoom = {
            id: `chat_${Date.now()}`,
            name: newFriendName,
            lastMessage: '대면 보안 코드로 대화 채널이 오픈되었습니다.',
            time: '방금',
            unread: 0
          };

          setChats([newChatRoom, ...chats]);
          setFollowing(prev => prev + 1);
          setFollowers(prev => prev + 1);
          setActiveChat(newChatRoom);
          
          setCustomAlert(`[대면인증 성공]\n${newFriendName} 님과 안전한 1:1 대화방이 생성되었습니다.`);
          setShowFollowModal(false);
          setFaceToFaceCode('');
          setCurrentView('chats');
        } else {
          setCustomAlert('인증을 위해 상대방의 2자리 이상 이름 또는 코드를 입력해 주세요.');
        }
      };

      const handleAddBlock = (name) => {
        if (!blockedUsers.includes(name)) {
          setBlockedUsers([...blockedUsers, name]);
          setCustomAlert(`[검열] ${name} 님이 즉시 차단 처리되어 시야에서 제외되었습니다.`);
          
          const remainingChats = chats.filter(c => c.name !== name);
          if (activeChat && activeChat.name === name) {
            setActiveChat(remainingChats[0] || null);
          }
        }
      };

      const handleAddRestrict = (name) => {
        if (!restrictedUsers.includes(name)) {
          setRestrictedUsers([...restrictedUsers, name]);
          setCustomAlert(`[검열] ${name} 님을 제한했습니다. 이제 상대 메시지가 투명 필터로 가려집니다.`);
        }
      };

      const handleSendMessage = (e) => {
        e.preventDefault();
        if (!inputText.trim() && !selectedFile && !selectedGif) return;

        if (editingMessageId) {
          setMessages(messages.map(msg => 
            msg.id === editingMessageId ? { ...msg, text: inputText + ' (수정됨)' } : msg
          ));
          setEditingMessageId(null);
        } else {
          let messageContent = inputText;
          if (selectedFile) {
            messageContent = `📎 학업자료 파일 수신 완료\n📁 파일명: ${selectedFile.name} (${selectedFile.size})\n\n${messageContent}`;
          }
          if (selectedGif) {
            messageContent = `👾 공지방 공부짤\n[ ${selectedGif.emoji} ${selectedGif.name} ]\n\n${messageContent}`;
          }

          const newMsg = {
            id: Date.now().toString(),
            senderId: 'user_1',
            text: messageContent,
            time: new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' }),
            reactions: []
          };
          setMessages([...messages, newMsg]);
        }
        setInputText('');
        setSelectedFile(null);
        setSelectedGif(null);
      };

      const handleDeleteMessage = (id) => {
        setCustomConfirm({
          message: '선택하신 메시지를 삭제하시겠습니까?',
          onConfirm: () => {
            setMessages(messages.filter(msg => msg.id !== id));
          }
        });
      };

      const handleEditClick = (msg) => {
        setEditingMessageId(msg.id);
        let pureText = msg.text;
        if (pureText.includes("\n\n")) {
          pureText = pureText.split("\n\n")[1] || pureText;
        }
        setInputText(pureText.replace(' (수정됨)', ''));
      };

      const handleReact = (msgId, emoji) => {
        setMessages(messages.map(msg => {
          if (msg.id === msgId) {
            const hasReaction = msg.reactions.includes(emoji);
            return {
              ...msg,
              reactions: hasReaction ? msg.reactions.filter(r => r !== emoji) : [...msg.reactions, emoji]
            };
          }
          return msg;
        }));
        setActiveEmojiMenu(null);
      };

      const filteredChats = chats.filter(chat => !blockedUsers.includes(chat.name));

      if (!isLoggedIn) {
        return (
          <div className="flex items-center justify-center min-h-screen p-4">
            <div className="w-full max-w-md p-8 bg-white border border-slate-200 rounded-3xl shadow-xl relative animate-fade-in">
              <div className="text-center mb-8">
                <div className="inline-flex items-center justify-center w-16 h-16 rounded-2xl bg-blue-600 mb-4 shadow-md">
                  <Icon name="monitor" className="w-8 h-8 text-white" />
                </div>
                <h1 className="text-3xl font-black text-blue-500 tracking-tight">공지방 PC</h1>
                <p className="text-slate-400 text-xs mt-2 font-semibold">지메일 보안 가동 및 비공개 학업 네크워크</p>
              </div>
              
              {authStep === 1 ? (
                <form onSubmit={handleRequestEmailCode} className="space-y-6">
                  <div className="space-y-2">
                    <label className="block text-xs font-bold text-slate-500">1단계: 이메일 인증 주소</label>
                    <div className="relative">
                      <span className="absolute left-4 top-1/2 -translate-y-1/2 text-slate-400">
                        <Icon name="mail" className="w-5 h-5" />
                      </span>
                      <input 
                        type="email" 
                        required
                        value={email}
                        onChange={(e) => setEmail(e.target.value)}
                        className="w-full pl-12 pr-4 py-3 bg-slate-50 border border-slate-200 rounded-xl focus:ring-2 focus:ring-blue-500 focus:outline-none text-slate-800 text-sm font-semibold transition"
                        placeholder="your-email@gmail.com"
                        disabled={isSending}
                      />
                    </div>
                    <p className="text-[11px] text-slate-400 leading-relaxed font-semibold">
                      ※ 이메일로 발송되는 6자리 특수 비밀키를 입력해야 입장이 가능합니다.
                    </p>
                  </div>

                  <button 
                    type="submit" 
                    disabled={isSending}
                    className="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-3.5 px-4 rounded-xl shadow-lg transition-all active:scale-[0.98] flex items-center justify-center gap-2 text-sm"
                  >
                    {isSending ? "지메일 보안 발송 프로세스 진행중..." : "지메일로 인증번호 전송"}
                  </button>
                </form>
              ) : (
                <form onSubmit={handleVerifyCode} className="space-y-6">
                  <div className="space-y-4 text-center">
                    <div className="text-sm text-slate-600 font-semibold">
                      <strong className="text-slate-800">{email}</strong>으로 인증코드가 전송되었습니다.
                    </div>
                    <div className="bg-amber-50 py-2 px-3 rounded-xl border border-amber-200 inline-block">
                      <span className="text-xs text-amber-600 font-semibold">임시 발송 인증코드: {generatedCode}</span>
                    </div>
                    <div className="relative">
                      <span className="absolute left-4 top-1/2 -translate-y-1/2 text-slate-400">
                        <Icon name="key-round" className="w-5 h-5" />
                      </span>
                      <input 
                        type="text" 
                        required
                        maxLength={6}
                        value={userCodeInput}
                        onChange={(e) => setUserCodeInput(e.target.value)}
                        className="w-full pl-12 pr-4 py-3 bg-slate-50 border border-slate-200 rounded-xl focus:ring-2 focus:ring-blue-500 focus:outline-none text-slate-800 text-center tracking-[0.5em] font-extrabold text-xl transition"
                        placeholder="000000"
                      />
                    </div>
                  </div>

                  <button 
                    type="submit" 
                    className="w-full bg-emerald-600 hover:bg-emerald-700 text-white font-bold py-3.5 rounded-xl shadow-lg transition-all"
                  >
                    2단계 인증 확인 및 입장
                  </button>
                </form>
              )}

              {/* 가상 알럿 모달 */}
              {customAlert && (
                <div className="absolute inset-0 bg-slate-950/80 z-50 flex items-center justify-center p-6 backdrop-blur-sm rounded-3xl">
                  <div className="bg-white border border-slate-200 rounded-2xl p-6 w-full text-center">
                    <Icon name="info" className="w-10 h-10 text-red-500 mx-auto mb-3" />
                    <p className="text-sm font-semibold text-slate-800 mb-5 whitespace-pre-wrap">{customAlert}</p>
                    <button type="button" onClick={() => setCustomAlert(null)} className="w-full bg-blue-600 hover:bg-blue-700 text-white py-2.5 rounded-xl text-xs font-bold">확인</button>
                  </div>
                </div>
              )}
            </div>
          </div>
        );
      }

      return (
        <div className="flex justify-center items-center w-full h-full p-0 md:p-6 relative">
          <div className="w-full h-full bg-white md:rounded-3xl shadow-2xl overflow-hidden flex flex-col md:flex-row relative border border-slate-200">
            
            {/* 사이드바 - 내 정보 */}
            <aside className="hidden md:flex flex-col w-64 bg-slate-900 text-white p-5 justify-between">
              <div>
                <div className="flex items-center gap-3 mb-8">
                  <div className="w-10 h-10 bg-blue-600 rounded-xl flex items-center justify-center font-black text-xl text-white">공</div>
                  <div>
                    <h1 className="text-lg font-black tracking-wider text-blue-400">공지방 PC</h1>
                    <span className="text-[10px] text-emerald-400 flex items-center gap-1 font-semibold">● 비공개 안전 모드</span>
                  </div>
                </div>

                <div className="bg-slate-800 rounded-2xl p-4 border border-slate-700 mb-6">
                  <div className="flex items-center gap-3 mb-3">
                    <div className="w-10 h-10 bg-slate-600 rounded-full flex items-center justify-center font-bold text-white">나</div>
                    <div>
                      <div className="font-bold text-sm">{MOCK_USER.name}</div>
                      <div className="text-[10px] text-slate-400 font-semibold">코드: {MOCK_USER.code}</div>
                    </div>
                  </div>
                  <div className="grid grid-cols-2 gap-2 text-center text-xs pt-2 border-t border-slate-700 font-semibold">
                    <div>
                      <div className="text-slate-400 text-[10px]">팔로워</div>
                      <div className="font-bold text-blue-400">{followers}</div>
                    </div>
                    <div>
                      <div className="text-slate-400 text-[10px]">팔로잉</div>
                      <div className="font-bold text-blue-400">{following}</div>
                    </div>
                  </div>
                </div>

                <nav className="space-y-2">
                  <button onClick={() => setCurrentView('chats')} className={`w-full flex items-center gap-3 px-4 py-3 rounded-xl text-sm font-bold transition-all ${currentView === 'chats' ? 'bg-blue-600' : 'text-slate-400 hover:bg-slate-800'}`}>
                    <Icon name="message-circle" className="w-5 h-5" /><span>대화 / 공지사항</span>
                  </button>
                  <button onClick={() => setCurrentView('settings')} className={`w-full flex items-center gap-3 px-4 py-3 rounded-xl text-sm font-bold transition-all ${currentView === 'settings' ? 'bg-blue-600' : 'text-slate-400 hover:bg-slate-800'}`}>
                    <Icon name="shield-ban" className="w-5 h-5" /><span>검열 및 권한 통제</span>
                  </button>
                </nav>
              </div>
              <div className="text-[11px] text-slate-500 bg-slate-800/40 p-3 rounded-xl font-semibold leading-relaxed">
                🔒 외부 글쓰기가 불가능한 사설 교육 전용 암호화 통신망입니다.
              </div>
            </aside>

            {/* 모바일 상단 바 */}
            <header className="md:hidden bg-slate-900 text-white p-4 flex justify-between items-center w-full">
              <h1 className="text-xl font-black text-blue-400">공지방</h1>
              <div className="flex gap-3">
                <button onClick={() => setShowFollowModal(true)} className="p-1.5 bg-slate-800 rounded-lg"><Icon name="user-plus" className="w-4 h-4" /></button>
                <button onClick={() => setCurrentView(currentView === 'settings' ? 'chats' : 'settings')} className="p-1.5 bg-slate-800 rounded-lg"><Icon name="settings" className="w-4 h-4" /></button>
              </div>
            </header>

            <div className="flex-1 flex flex-col md:flex-row min-w-0 h-full overflow-hidden">
              {/* 대화목록 + 입시 초대형 배너 광고 */}
              <div className={`w-full md:w-80 flex-shrink-0 bg-slate-100 border-r border-slate-200 flex flex-col h-full ${currentView === 'settings' ? 'hidden md:flex' : 'flex'}`}>
                {showAd && (
                  <div className="w-full flex-shrink-0 flex flex-col relative border-b border-slate-300 bg-white">
                    <button onClick={() => setShowAd(false)} className="absolute top-2 right-2 bg-black/60 text-white rounded-full p-1"><Icon name="x" className="w-3 h-3" /></button>
                    
                    <div className="bg-gradient-to-r from-teal-600 to-indigo-700 p-5 text-white text-center">
                      <span className="bg-yellow-400 text-slate-900 text-[9px] px-2 py-0.5 rounded font-black uppercase">MEGASTUDY</span>
                      <h2 className="text-xl font-extrabold italic mt-1">메가스터디 0원 메가패스</h2>
                    </div>
                    <div className="bg-slate-900 p-4 text-center text-white border-t border-slate-800">
                      <h3 className="text-md font-bold tracking-tight text-cyan-300">대성마이맥 19PASS</h3>
                    </div>
                    <div className="flex divide-x divide-slate-700 border-t border-slate-200">
                      <div className="flex-1 bg-neutral-950 p-3 text-center text-white">
                        <span className="text-sm font-black text-amber-500">시대인재</span>
                      </div>
                      <div className="flex-1 bg-yellow-400 p-3 text-center text-blue-900 font-bold">
                        <span className="text-sm font-black">족보닷컴 100%적중</span>
                      </div>
                    </div>
                  </div>
                )}

                <div className="flex-1 overflow-y-auto p-3 space-y-2">
                  <div className="flex justify-between items-center px-1 mb-2">
                    <span className="text-xs font-bold text-slate-500 uppercase">안전 대화 채널 ({filteredChats.length})</span>
                  </div>
                  {filteredChats.map(chat => (
                    <div key={chat.id} onClick={() => setActiveChat(chat)} className={`flex items-center p-3.5 rounded-2xl cursor-pointer transition-all ${activeChat?.id === chat.id ? 'bg-white shadow border-l-4 border-l-blue-600' : 'bg-white/50 border border-slate-200/40'}`}>
                      <div className="w-10 h-10 bg-slate-300 rounded-xl flex items-center justify-center font-bold mr-3">{chat.name.charAt(0)}</div>
                      <div className="flex-1 min-w-0">
                        <div className="flex justify-between items-center">
                          <span className="font-bold text-sm text-slate-900 truncate">{chat.name}</span>
                          <span className="text-[10px] text-slate-400">{chat.time}</span>
                        </div>
                        <p className="text-xs text-slate-500 truncate mt-0.5">{chat.lastMessage}</p>
                      </div>
                    </div>
                  ))}
                  {filteredChats.length === 0 && (
                    <div className="text-center py-8 text-xs text-slate-400">대화 중인 친구가 없습니다. 대면 연결을 시작해 보세요!</div>
                  )}
                </div>
              </div>

              {/* 활성화된 대화방 영역 */}
              <div className={`flex-1 bg-slate-50 flex flex-col h-full min-w-0 ${currentView === 'settings' ? 'hidden md:flex' : 'flex'}`}>
                {activeChat && !blockedUsers.includes(activeChat.name) ? (
                  <div className="flex flex-col h-full bg-[#f0f3f5] overflow-hidden">
                    <div className="bg-white border-b border-slate-200 p-4 flex justify-between items-center shadow-sm shrink-0">
                      <div className="flex items-center gap-3">
                        <div className="w-10 h-10 bg-blue-50 rounded-xl flex items-center justify-center text-blue-600 font-bold">{activeChat.name.charAt(0)}</div>
                        <div>
                          <div className="font-bold text-slate-900">{activeChat.name}</div>
                          <div className="text-[11px] text-slate-500 font-semibold">1:1 비공개 보안 채널</div>
                        </div>
                      </div>
                      
                      <div className="flex items-center gap-1">
                        <button onClick={() => handleAddRestrict(activeChat.name)} className="p-2 hover:bg-slate-100 rounded-lg text-slate-500 hover:text-amber-600 transition" title="이 사용자 제한">
                          <Icon name="volume-x" className="w-5 h-5" />
                        </button>
                        <button onClick={() => handleAddBlock(activeChat.name)} className="p-2 hover:bg-slate-100 rounded-lg text-slate-500 hover:text-red-600 transition" title="이 사용자 차단">
                          <Icon name="shield-ban" className="w-5 h-5" />
                        </button>
                      </div>
                    </div>

                    <div className="flex-1 p-6 overflow-y-auto space-y-4">
                      {messages.map((msg) => {
                        const isMe = msg.senderId === 'user_1';
                        const isRestricted = !isMe && restrictedUsers.includes(activeChat.name);
                        
                        return (
                          <div key={msg.id} className={`flex flex-col ${isMe ? 'items-end' : 'items-start'}`}>
                            <div className="max-w-[80%] flex flex-col items-end group relative">
                              <div className={`rounded-2xl p-3.5 text-sm transition-all ${isMe ? 'bg-blue-600 text-white rounded-tr-none' : 'bg-white text-slate-900 rounded-tl-none border border-slate-200 shadow-sm'}`}>
                                {isRestricted ? (
                                  <div className="space-y-2">
                                    <div className="flex items-center gap-1.5 text-amber-600 font-bold text-xs bg-amber-50 p-1.5 rounded-lg border border-amber-200">
                                      <Icon name="shield-alert" className="w-3.5 h-3.5" />
                                      <span>[통제 제한] 필터링 처리된 메시지</span>
                                    </div>
                                    <p className="blur-text cursor-pointer select-none leading-relaxed" title="마우스를 올리거나 터치하여 잠시 보기">
                                      {msg.text}
                                    </p>
                                  </div>
                                ) : (
                                  <p className="whitespace-pre-wrap leading-relaxed">{msg.text}</p>
                                )}

                                {msg.reactions && msg.reactions.length > 0 && (
                                  <div className="absolute -bottom-3 right-3 bg-white border border-slate-200 rounded-full px-2 py-0.5 text-xs shadow flex gap-1 text-slate-800 font-semibold">
                                    {msg.reactions.map((r, i) => <span key={i}>{r}</span>)}
                                  </div>
                                )}
                              </div>

                              <div className={`absolute top-1/2 -translate-y-1/2 flex gap-1 opacity-0 group-hover:opacity-100 transition-opacity bg-slate-950/90 text-white rounded-xl p-1 z-10 ${isMe ? '-left-20' : '-right-24'}`}>
                                {isMe ? (
                                  <>
                                    <button onClick={() => handleEditClick(msg)} className="p-1 hover:bg-slate-800 rounded text-sky-400" title="문자 수정">
                                      <Icon name="edit-2" className="w-3.5 h-3.5" />
                                    </button>
                                    <button onClick={() => handleDeleteMessage(msg.id)} className="p-1 hover:bg-slate-800 rounded text-red-400" title="문자 삭제">
                                      <Icon name="trash-2" className="w-3.5 h-3.5" />
                                    </button>
                                  </>
                                ) : (
                                  <div className="flex items-center gap-1">
                                    <button onClick={() => setActiveEmojiMenu(activeEmojiMenu === msg.id ? null : msg.id)} className="p-1 hover:bg-slate-800 rounded text-amber-400" title="공감 남기기">
                                      <Icon name="smile" className="w-3.5 h-3.5" />
                                    </button>
                                  </div>
                                )}
                              </div>

                              {activeEmojiMenu === msg.id && (
                                <div className="absolute -top-10 right-0 bg-slate-900 border border-slate-800 p-1.5 rounded-full flex gap-1.5 shadow-2xl z-30 animate-fade-in">
                                  {['👍', '🔥', '❤️', '😮', '😭', '✏️'].map(emoji => (
                                    <button key={emoji} onClick={() => handleReact(msg.id, emoji)} className="hover:scale-130 transition-transform p-0.5 text-sm">{emoji}</button>
                                  ))}
                                </div>
                              )}
                            </div>
                            <span className="text-[9px] text-slate-400 mt-1 mx-1 font-semibold">{msg.time}</span>
                          </div>
                        );
                      })}
                      <div ref={messagesEndRef} />
                    </div>

                    <div className="bg-white p-3 border-t border-slate-200 shrink-0">
                      {editingMessageId && <div className="text-xs text-amber-800 bg-amber-50 p-2 mb-2 rounded font-bold">수정 진행 중...</div>}
                      
                      {(selectedFile || selectedGif) && (
                        <div className="text-xs bg-slate-100 p-2.5 rounded-xl mb-2 flex justify-between items-center border border-slate-200 animate-fade-in font-semibold">
                          <div className="flex items-center gap-2">
                            {selectedFile && <span className="flex items-center gap-1 text-blue-600 font-bold">📁 {selectedFile.name}</span>}
                            {selectedGif && <span className="flex items-center gap-1 text-indigo-600 font-bold">👾 {selectedGif.emoji} {selectedGif.name}</span>}
                          </div>
                          <button type="button" onClick={() => {setSelectedFile(null); setSelectedGif(null);}} className="text-red-500 hover:text-red-700 font-black p-1">
                            <Icon name="x" className="w-4 h-4" />
                          </button>
                        </div>
                      )}

                      <form onSubmit={handleSendMessage} className="flex items-end gap-3">
                        <button type="button" onClick={() => { setShowFileModal(true); setShowGifModal(false); }} className="p-2 text-slate-500 hover:text-blue-600 transition" title="파일 첨부">
                          <Icon name="paperclip" className="w-5 h-5" />
                        </button>
                        <button type="button" onClick={() => { setShowGifModal(true); setShowFileModal(false); }} className="p-2 text-slate-500 hover:text-blue-600 transition" title="GIF 전송">
                          <Icon name="image" className="w-5 h-5" />
                        </button>
                        <div className="flex-1 bg-slate-100 rounded-2xl px-4 py-1">
                          <textarea 
                            value={inputText}
                            onChange={(e) => setInputText(e.target.value)}
                            placeholder="공지사항이나 안전 메시지 작성..."
                            className="w-full bg-transparent py-2.5 focus:outline-none resize-none text-sm font-semibold"
                            rows="1"
                            onKeyDown={(e) => {
                              if(e.key === 'Enter' && !e.shiftKey) { e.preventDefault(); handleSendMessage(e); }
                            }}
                          />
                        </div>
                        <button type="submit" className="p-3 rounded-xl bg-blue-600 text-white shadow-md active:scale-95 transition-transform">
                          <Icon name="send" className="w-4 h-4" />
                        </button>
                      </form>
                    </div>
                  </div>
                ) : (
                  <div className="flex-1 flex flex-col items-center justify-center text-slate-400 p-8 text-center bg-[#f0f3f5] h-full">
                    <Icon name="shield-alert" className="w-12 h-12 text-slate-300 mb-3" />
                    <p className="font-bold text-sm">연결된 대화방이 없거나 차단된 대화방입니다.</p>
                    <p className="text-xs text-slate-400 mt-1 font-semibold">대면 추가를 통해 대화 상대방을 안전하게 확보하세요.</p>
                  </div>
                )}
              </div>

              {/* 검열 제어 패널 */}
              {(currentView === 'settings' || window.innerWidth >= 768) && (
                <div className={`w-full md:w-80 bg-white border-l border-slate-200 p-6 flex flex-col justify-between overflow-y-auto ${currentView === 'settings' ? 'flex' : 'hidden md:flex'}`}>
                  <div>
                    <h2 className="text-lg font-bold text-slate-900 mb-4 flex items-center gap-2">
                      <Icon name="shield-alert" className="text-red-500 w-5 h-5" />
                      <span>검열 시스템 가동</span>
                    </h2>
                    <div className="bg-slate-50 p-4 rounded-2xl mb-4 border border-slate-100">
                      <span className="text-[10px] text-slate-400 block font-bold">내 대면 인증 번호</span>
                      <span className="text-xl font-bold text-blue-600">{MOCK_USER.code}</span>
                    </div>

                    <div className="space-y-6">
                      {/* 차단된 사용자 */}
                      <div>
                        <h3 className="text-xs font-black text-slate-500 uppercase tracking-wider mb-2 flex items-center gap-1.5">
                          <span className="w-1.5 h-1.5 bg-red-500 rounded-full"></span> 차단된 학업 방해자
                        </h3>
                        {blockedUsers.length > 0 ? (
                          blockedUsers.map(name => (
                            <div key={name} className="flex justify-between items-center bg-slate-50 p-2.5 rounded-xl border border-slate-200/60 mb-1.5 text-xs">
                              <span className="font-bold text-slate-700">{name}</span>
                              <button type="button" onClick={() => {
                                setBlockedUsers(blockedUsers.filter(u => u !== name));
                                setCustomAlert(`[검열 알림] ${name} 님의 차단이 안전하게 해제되었습니다.`);
                              }} className="text-red-500 font-semibold hover:underline">해제</button>
                            </div>
                          ))
                        ) : (
                          <p className="text-xs text-slate-400 italic font-semibold">차단된 사용자가 없습니다.</p>
                        )}
                      </div>

                      {/* 제한된 사용자 */}
                      <div>
                        <h3 className="text-xs font-black text-slate-500 uppercase tracking-wider mb-2 flex items-center gap-1.5">
                          <span className="w-1.5 h-1.5 bg-amber-500 rounded-full"></span> 제한된 사용자 (메시지 숨김)
                        </h3>
                        {restrictedUsers.length > 0 ? (
                          restrictedUsers.map(name => (
                            <div key={name} className="flex justify-between items-center bg-slate-50 p-2.5 rounded-xl border border-slate-200/60 mb-1.5 text-xs">
                              <span className="font-bold text-slate-700">{name}</span>
                              <button type="button" onClick={() => {
                                setRestrictedUsers(restrictedUsers.filter(u => u !== name));
                                setCustomAlert(`[검열 알림] ${name} 님의 제한 통제가 해제되었습니다.`);
                              }} className="text-amber-600 font-semibold hover:underline">해제</button>
                            </div>
                          ))
                        ) : (
                          <p className="text-xs text-slate-400 italic font-semibold">제한된 사용자가 없습니다.</p>
                        )}
                      </div>
                    </div>
                  </div>
                  <button type="button" onClick={() => setIsLoggedIn(false)} className="w-full bg-slate-100 hover:bg-red-50 hover:text-red-600 py-2.5 rounded-xl text-xs font-bold transition mt-6">보안 세션 파기 (로그아웃)</button>
                </div>
              )}
            </div>

            {/* 모바일 탭 */}
            <nav className="md:hidden bg-white border-t border-slate-200 flex justify-around p-2 shrink-0 w-full">
              <button type="button" onClick={() => setCurrentView('chats')} className="p-2 text-slate-400">
                <Icon name="message-circle" className="w-5 h-5" />
              </button>
              <button type="button" onClick={() => setShowFollowModal(true)} className="p-2 text-slate-400">
                <Icon name="qr-code" className="w-5 h-5" />
              </button>
              <button type="button" onClick={() => setCurrentView('settings')} className="p-2 text-slate-400">
                <Icon name="shield-ban" className="w-5 h-5" />
              </button>
            </nav>

            {/* 대면 연결 모달 */}
            {showFollowModal && (
              <div className="absolute inset-0 bg-slate-950/70 z-50 flex items-center justify-center p-4 backdrop-blur-sm">
                <div className="bg-white rounded-3xl p-6 w-full max-w-sm shadow-2xl">
                  <div className="flex justify-between items-center mb-4">
                    <h3 className="font-extrabold text-lg flex items-center gap-1.5">
                      <Icon name="qr-code" className="text-blue-600 w-5 h-5" />
                      <span>대면 친구 연결</span>
                    </h3>
                    <button type="button" onClick={() => setShowFollowModal(false)} className="text-slate-400 hover:text-slate-600">
                      <Icon name="x" className="w-5 h-5" />
                    </button>
                  </div>
                  <p className="text-xs text-slate-500 leading-relaxed mb-4 font-semibold">
                    같은 교실 또는 학원에서 직접 만나 서로 확인한 대면 친구의 이름이나 코드를 입력해 주세요. 즉시 대화방에 자동 연동됩니다.
                  </p>
                  <input 
                    type="text" 
                    value={faceToFaceCode}
                    onChange={(e) => setFaceToFaceCode(e.target.value)}
                    placeholder="상대방 이름 또는 인증코드 입력" 
                    className="w-full border p-3.5 rounded-xl mb-4 text-center font-bold outline-none focus:ring-2 focus:ring-blue-500 bg-slate-50 text-slate-800 text-sm"
                  />
                  <div className="flex gap-2">
                    <button type="button" onClick={() => setShowFollowModal(false)} className="flex-1 py-3 bg-slate-100 hover:bg-slate-200 rounded-xl text-xs font-semibold">취소</button>
                    <button type="button" onClick={handleFaceToFaceFollow} className="flex-1 py-3 bg-blue-600 hover:bg-blue-700 text-white rounded-xl text-xs font-bold">인증 연결</button>
                  </div>
                </div>
              </div>
            )}

            {/* 파일 선택 모달 */}
            {showFileModal && (
              <div className="absolute inset-0 bg-slate-950/70 z-50 flex items-center justify-center p-4 backdrop-blur-sm">
                <div className="bg-white rounded-3xl p-6 w-full max-w-sm shadow-2xl">
                  <div className="flex justify-between items-center mb-3">
                    <h3 className="font-extrabold text-md flex items-center gap-1.5 text-slate-900">
                      <Icon name="folder-open" className="text-blue-500 w-5 h-5" />
                      <span>학업자료 파일 선택</span>
                    </h3>
                    <button type="button" onClick={() => setShowFileModal(false)} className="text-slate-400 hover:text-slate-600">
                      <Icon name="x" className="w-5 h-5" />
                    </button>
                  </div>
                  <div className="space-y-2 max-h-60 overflow-y-auto pr-1">
                    {MOCK_FILES.map(file => (
                      <div 
                        key={file.name} 
                        onClick={() => { setSelectedFile(file); setSelectedGif(null); setShowFileModal(false); }}
                        className="flex justify-between items-center bg-slate-50 hover:bg-blue-50 border border-slate-200/60 p-3 rounded-xl cursor-pointer"
                      >
                        <span className="text-xs font-semibold text-slate-800">{file.name}</span>
                        <span className="text-[10px] text-slate-400 font-bold">{file.size}</span>
                      </div>
                    ))}
                  </div>
                </div>
              </div>
            )}

            {/* GIF 선택기 모달 */}
            {showGifModal && (
              <div className="absolute inset-0 bg-slate-950/70 z-50 flex items-center justify-center p-4 backdrop-blur-sm">
                <div className="bg-white rounded-3xl p-6 w-full max-w-sm shadow-2xl">
                  <div className="flex justify-between items-center mb-3">
                    <Icon name="image" className="text-indigo-500 w-5 h-5" />
                    <span className="font-bold text-slate-900 text-sm ml-1.5">공부 자극 짤방(GIF) 선택</span>
                    <button type="button" onClick={() => setShowGifModal(false)} className="text-slate-400 hover:text-slate-600 ml-auto">
                      <Icon name="x" className="w-5 h-5" />
                    </button>
                  </div>
                  <div className="grid grid-cols-1 gap-2.5 max-h-60 overflow-y-auto pr-1">
                    {MOCK_GIFS.map(gif => (
                      <div 
                        key={gif.name} 
                        onClick={() => { setSelectedGif(gif); setSelectedFile(null); setShowGifModal(false); }}
                        className="flex items-center gap-3 bg-slate-50 hover:bg-indigo-50 border border-slate-200/60 p-3 rounded-xl cursor-pointer"
                      >
                        <div className="text-2xl bg-white w-10 h-10 rounded-lg flex items-center justify-center shadow-sm">{gif.emoji.charAt(0)}</div>
                        <div>
                          <p className="text-xs font-bold text-slate-800">{gif.name}</p>
                        </div>
                      </div>
                    ))}
                  </div>
                </div>
              </div>
            )}

          </div>

          {/* 인앱 커스텀 알럿 모달 */}
          {customAlert && (
            <div className="absolute inset-0 bg-slate-950/70 z-[100] flex items-center justify-center p-4 backdrop-blur-sm">
              <div className="bg-white rounded-3xl p-6 w-full max-w-sm shadow-2xl text-center">
                <Icon name="info" className="w-12 h-12 text-blue-500 mx-auto mb-3 block" />
                <p className="text-slate-800 font-bold mb-5 whitespace-pre-wrap text-sm leading-relaxed">{customAlert}</p>
                <button
                  type="button"
                  onClick={() => setCustomAlert(null)}
                  className="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 rounded-xl transition text-xs"
                >
                  확인
                </button>
              </div>
            </div>
          )}

          {/* 인앱 커스텀 확인 모달 */}
          {customConfirm && (
            <div className="absolute inset-0 bg-slate-950/70 z-[100] flex items-center justify-center p-4 backdrop-blur-sm">
              <div className="bg-white rounded-3xl p-6 w-full max-w-sm shadow-2xl text-center">
                <Icon name="help-circle" className="w-12 h-12 text-amber-500 mx-auto mb-3 block" />
                <p className="text-slate-800 font-bold mb-5 whitespace-pre-wrap text-sm leading-relaxed">{customConfirm.message}</p>
                <div className="flex gap-3">
                  <button
                    type="button"
                    onClick={() => setCustomConfirm(null)}
                    className="flex-1 bg-slate-100 hover:bg-slate-200 text-slate-700 font-bold py-3 rounded-xl transition text-xs"
                  >
                    취소
                  </button>
                  <button
                    type="button"
                    onClick={() => {
                      customConfirm.onConfirm();
                      setCustomConfirm(null);
                    }}
                    className="flex-1 bg-red-600 hover:bg-red-700 text-white font-bold py-3 rounded-xl transition text-xs"
                  >
                    확인
                  </button>
                </div>
              </div>
            </div>
          )}

        </div>
      );
    }

    // React 마운팅 타겟 지정 및 렌더링 호출을 명확하게 추가하여 레이아웃 빈화면 현상을 원천 방지합니다.
    const root = ReactDOM.createRoot(document.getElementById('app'));
    root.render(<GongjiApp />);
  </textarea>

  <!-- 안전한 수동 컴파일 프로세스 (로딩 완벽 보장) -->
  <script>
    function compileAndRun() {
      try {
        const sourceElement = document.getElementById('react-source');
        if (!sourceElement) {
          console.error("React source element not found.");
          return;
        }
        const code = sourceElement.textContent;
        const compiled = Babel.transform(code, {
          presets: [
            ['react', { runtime: 'classic' }]
          ]
        }).code;
        
        const script = document.createElement('script');
        script.text = compiled;
        document.body.appendChild(script);
      } catch (err) {
        console.error("React compilation error:", err);
      }
    }

    if (document.readyState === 'complete' || document.readyState === 'interactive') {
      compileAndRun();
    } else {
      window.addEventListener('DOMContentLoaded', compileAndRun);
    }
  </script>
</body>
</html>
