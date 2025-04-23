
# PANDA Adventure  
**Sinh viên:** KIM NGỌC SƠN  
**Mã sinh viên:** 23021437  

## 🎮 Giới thiệu chủ đề game  
**PANDA Adventure** là một trò chơi dạng platformer, nơi người chơi điều khiển một chú gấu trúc dễ thương vượt qua các thử thách, thu thập vật phẩm và tránh cạm bẫy nguy hiểm.  

**Cách chơi**: Sử dụng phím `>` để di chuyển sang phải, phím `<` để di chuyển sang trái. Di chuyển để thu thập item và tránh cạm bẫy.

---

## 🎯 Ngưỡng điểm mong muốn: **8 điểm**

### 🧠 Các tính năng tự làm – tự học

1. **Quản lý trạng thái trò chơi (State Machine)**  
   - Sử dụng `enum GameState` với các trạng thái: `MENU`, `PLAYING`, `PAUSE`, `GAME_OVER`, `HIGH_SCORES`, `SETTINGS`, `STORY`, `EXIT`.  
   - Điều khiển luồng trò chơi bằng `switch-case` trong các hàm `handleEvents()`, `update()`, `render()`.

2. **Hệ thống menu tương tác**  
   - Hiển thị menu chính với các mục: Bắt đầu, Xem điểm cao, Cài đặt, Câu chuyện, Thoát.  
   - Xử lý chọn menu bằng biến `menuOption` và `startGame`.

3. **Giao diện Pause và Game Over**  
   - Hiển thị giao diện tạm dừng, cho phép tiếp tục hoặc quay lại menu.  
   - Màn hình Game Over hiển thị điểm và cho phép chơi lại.

4. **Câu chuyện và phần hướng dẫn (Story)**  
   - Hiển thị cốt truyện giúp tăng chiều sâu cho game (thông qua lớp `Story`).

5. **Quản lý điểm (ScoreManager)**  
   - Tính toán điểm, lưu và hiển thị điểm cao từ file ngoài `highscore.txt`.  
   - Hiển thị font tuỳ chỉnh (`ARCADECLASSIC.TTF`).

6. **Hệ thống vật phẩm và hiệu ứng (Item Effect)**  
   - Vật phẩm sinh ngẫu nhiên: `PEACH`, `BAMBOO`, `TRAP`, `ROCK`, `HONEY`, `X2`.  
   - Mỗi vật phẩm có hiệu ứng riêng: tăng điểm, làm chậm tốc độ, nhân đôi điểm, kết thúc game.

7. **Tăng độ khó theo thời gian**  
   - Tốc độ game (`gameSpeed`) tăng mỗi 600 frame (~10 giây), tạo cảm giác thử thách dần.

8. **Hiệu ứng âm thanh**  
   - Âm thanh khi chọn menu, ăn item, hoặc khi thua game.

---

### 🧮 Các thuật toán đã cài đặt

1. **Thuật toán sinh vật phẩm ngẫu nhiên (Randomized Item Spawner)**  
   - Sử dụng `rand()` với xác suất: 5% là `X2`, 5% là `HONEY`, 22% là `PEACH`, v.v...  
   - Item được sinh ngẫu nhiên theo 3 làn đường (lane-based spawner).

2. **Thuật toán va chạm (Collision Detection)**  
   - Dùng `SDL_HasIntersection()` để phát hiện va chạm giữa người chơi và item.  
   - Phản ứng dựa trên loại item: tăng điểm, nhân đôi điểm, làm chậm, kết thúc game.

3. **Thuật toán xóa item không cần thiết**  
   - Item bị xóa nếu đã tương tác hoặc ra khỏi màn hình.

4. **Hệ thống đếm thời gian hiệu ứng (Effect Duration Timer)**  
   - Sử dụng `slowTimer` và `doubleScoreTimer` để kiểm soát thời gian hiệu lực của hiệu ứng `HONEY` và `X2`.

5. **Reset trạng thái game khi chơi lại**  
   - Reset các biến quan trọng như `frameCount`, `itemSpawnCounter`, `isSlowed`, `isDoubleScore`, v.v.

---

## 📚 Nguồn tham khảo

- **Tutorial học SDL2**:  
  - [Lazy Foo' Productions SDL2 Tutorials](https://lazyfoo.net/tutorials/SDL/)  
  - [Youtube - SDL2 Game Development](https://www.youtube.com/watch?v=MeMPCsqQzT0)

- **Nguồn ảnh/âm thanh**:  
  - Ảnh nhân vật: [https://www.freepik.com/free-vector/cute-panda-game-character](https://www.freepik.com/free-vector/cute-panda-game-character)  
  - Item và hiệu ứng: [https://opengameart.org](https://opengameart.org)  
  - Âm thanh:  
    - Click Menu / Game Over: `555611cd-7939-42dd-99e4-b461b93c900e.wav`  
      → **Nguồn**: *Chưa rõ – vui lòng cập nhật nếu có*  
      → Dạng file `.wav`, sử dụng khi người chơi chọn menu hoặc kết thúc trò chơi.

---

## 🤖 Mức độ sử dụng AI  
- Có sử dụng ChatGPT để hỗ trợ hiểu đoạn mã SDL, tối ưu logic và soát lỗi.  
- Mọi tính năng đều do bản thân tự viết, hiểu và sẵn sàng giải thích kỹ lưỡng khi vấn đáp.

---

## 🌟 Điểm nổi bật nếu hướng đến 9-10 điểm  
- Giao diện trực quan, có hoạt ảnh chuyển động bằng sprite sheet.  
- Có phần cốt truyện, hệ thống điểm cao, độ khó tăng dần.  
- Kết hợp hình ảnh, âm thanh, trạng thái và hiệu ứng để tạo trải nghiệm mượt mà, hoàn chỉnh.
