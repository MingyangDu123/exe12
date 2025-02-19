import cv2
import os

output_folder = "capture_video"
cam = cv2.VideoCapture(0)

frame_width = int(cam.get(cv2.CAP_PROP_FRAME_WIDTH))
frame_height = int(cam.get(cv2.CAP_PROP_FRAME_HEIGHT))

frame_count = 0

if not cam.isOpened():
    print("Could not open camera")
    exit()

while True:
    ret, frame = cam.read()

    if not ret:
        print("Could not read frame")
        break

    cv2.imshow('Camera', frame)

    if frame_count % 10 == 0:
        frame_filename = os.path.join(output_folder, f"frame_{frame_count}.jpg")
        cv2.imwrite(frame_filename, frame)
        print(f"Saved {frame_filename}")
    frame_count += 1

    if cv2.waitKey(1) == ord('q'):
        break

cam.release()
cv2.destroyAllWindows()
