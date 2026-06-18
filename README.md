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
